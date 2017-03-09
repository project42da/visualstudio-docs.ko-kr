---
title: "CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2102"
  - "CatchNonClsCompliantExceptionsInGeneralHandlers"
helpviewer_keywords: 
  - "CA2102"
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|  
|CheckId|CA2102|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute>로 표시되지 않았거나 `RuntimeCompatibility(WrapNonExceptionThrows = false)`로 표시된 어셈블리의 멤버에는 <xref:System.Exception?displayProperty=fullName>을 처리하는 catch 블록이 포함되며 바로 다음에 나오는 일반 catch 블록은 포함되지 않습니다.  이 규칙은 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 어셈블리는 무시합니다.  
  
## 규칙 설명  
 <xref:System.Exception>을 처리하는 catch 블록에서는 모든 CLS\(공용 언어 사양\) 규격 예외를 catch합니다.  그러나 CLS 규격이 아닌 예외는 catch되지 않습니다.  CLS 규격이 아닌 예외는 네이티브 코드 또는 MSIL\(Microsoft intermediate language\) 어셈블러에서 생성한 관리 코드에서 throw될 수 있습니다.  C\# 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에서는 CLS 규격이 아닌 예외를 throw할 수 없으며, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 CLS 규격이 아닌 예외를 catch하지 않습니다.  catch 블록으로 모든 예외를 처리하려는 경우 다음과 같은 일반 catch 블록 구문을 사용합니다.  
  
-   C\#: `catch {}`  
  
-   C\+\+: `catch(...) {}` 또는 `catch(Object^) {}`  
  
 catch 블록에서 이전에 허용됐던 권한이 제거되면 처리되지 않은 CLS 비규격 예외는 보안 문제가 됩니다.  CLS 비규격 예외는 catch되지 않으므로 CLS 비규격 예외를 throw하는 악의적인 메서드는 높은 권한으로 실행할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 모든 예외를 catch하려는 경우 이 규칙 위반 문제를 해결하려면 일반 catch 블록을 대체 또는 추가하거나 어셈블리를 `RuntimeCompatibility(WrapNonExceptionThrows = true)`로 표시합니다.  catch 블록에서 권한이 제거된 경우에는 일반 catch 블록에서 기능을 복제합니다.  모든 예외를 처리하려는 경우가 아니라면 <xref:System.Exception>을 처리하는 catch 블록을 특정 예외 형식을 처리하는 catch 블록으로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 try 블록에 CLS 비규격 예외를 생성할 수 있는 문이 없는 경우 이 규칙에서 경고를 표시하지 않아도 안전합니다.  네이티브 코드나 관리 코드에서는 CLS 비규격 예외를 throw할 수 있으므로 이러한 경우에는 try 블록 내에 있는 모든 코드 경로에서 실행할 수 있는 모든 코드에 대해 알아야 합니다.  공용 언어 런타임에서는 CLS 규격이 아닌 예외를 throw하지 않습니다.  
  
## 예제  
 다음 예제에서는 CLS 비규격 예외를 throw하는 MSIL 클래스를 보여 줍니다.  
  
```  
.assembly ThrowNonClsCompliantException {}  
.class public auto ansi beforefieldinit ThrowsExceptions  
{  
   .method public hidebysig static void  
         ThrowNonClsException() cil managed  
   {  
      .maxstack  1  
      IL_0000:  newobj     instance void [mscorlib]System.Object::.ctor()  
      IL_0005:  throw  
   }  
}  
```  
  
## 예제  
 다음 예제에서는 이 규칙에 맞는 일반 catch 블록이 있는 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]  
  
 위의 코드 예제를 다음과 같이 컴파일합니다.  
  
```  
ilasm /dll ThrowNonClsCompliantException.il  
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs  
```  
  
## 관련 규칙  
 [CA1031: 일반적인 예외 형식을 catch하지 마십시오.](../Topic/CA1031:%20Do%20not%20catch%20general%20exception%20types.md)  
  
## 참고 항목  
 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)   
 [Ilasm.exe\(IL 어셈블러\)](../Topic/Ilasm.exe%20\(IL%20Assembler\).md)   
 [Overriding Security Checks](http://msdn.microsoft.com/ko-kr/4acdeff5-fc05-41bf-8505-7387cdbfca28)   
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)