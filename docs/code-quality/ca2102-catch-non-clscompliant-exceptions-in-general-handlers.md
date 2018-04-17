---
title: 'CA2102: 일반 처리기에서 비 CLSCompliant 예외를 Catch | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cff8d36cd80a31cf05ca461730d51703afc106ee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하십시오.
|||  
|-|-|  
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|  
|CheckId|CA2102|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 로 표시 되지 않으면 어셈블리의 멤버는 <xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute> 또는 표시 되어 `RuntimeCompatibility(WrapNonExceptionThrows = false)` 를 처리 하는 catch 블록이 포함 <xref:System.Exception?displayProperty=fullName> 되며 바로 뒤의 일반 catch 블록은 포함 되지 않습니다. 이 규칙은 무시 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 어셈블리입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 처리 하는 catch 블록 <xref:System.Exception> 모든 공용 언어 사양 (CLS) 규격이 예외를 catch 합니다. 그러나 비 CLS 규격이 아닌 예외를 catch 하지 않습니다. 비 CLS 규격이 예외 또는 관리 되는 코드는 Microsoft에서 생성 된 네이티브 코드에서 throw 될 수에 대 한 MSIL (language) 약간 어셈블러 합니다. C# 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러 비 CLS 규격 예외가 throw 되도록 허용 하지 않습니다 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 비 CLS 규격이 아닌 예외를 catch 하지 않습니다. Catch 블록의 의도 모든 예외를 처리할 경우 다음 일반 catch 블록 구문을 사용 합니다.  
  
-   C#: `catch {}`  
  
-   C + +: `catch(...) {}` 또는 `catch(Object^) {}`  
  
 처리 되지 않은 비 CLS 비규격 예외 catch 블록에서 이전에 허용 된 권한 제거 되는 보안 문제가 됩니다. 비 CLS 규격이 아닌 예외를 발견 하지 및 때문에 비 CLS 비규격 예외를 throw 하는 악성 메서드는 승격 된 권한으로 실행 수 없습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 모든 catch 하는 경우이 규칙 위반 문제를 해결 하려면 예외, 대체 또는 일반 catch 블록을 추가 하거나 어셈블리 표시 `RuntimeCompatibility(WrapNonExceptionThrows = true)`합니다. Catch 블록에서 사용 권한을 제거 하는 경우 중복 기능 일반에서 catch 블록입니다. 이 모든 예외를 처리 하려는 경우를 처리 하는 catch 블록을 대체 <xref:System.Exception> 특정 예외 형식을 처리 하는 catch 블록으로 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 Try 블록 비 CLS 비규격 예외가 생성 하는 모든 문이 포함 되어 있지 않으면이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 네이티브 또는 관리 코드 비 CLS 비규격 예외 throw 할 수 있습니다, 때문에이 try 블록 내의 모든 코드 경로에 실행 될 수 있는 모든 코드에 대 한 지식이 필요 합니다. 공용 언어 런타임에 의해 비 CLS 규격 예외가 throw 되지 않습니다 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 비 CLS 비규격 예외를 throw 하는 MSIL 클래스를 보여 줍니다.  
  
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
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 충족 하는 일반 catch 블록을 포함 하는 메서드를 보여 줍니다.  
  
 [!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]  
  
 다음과 같이 앞의 예제를 컴파일하십시오.  
  
```  
ilasm /dll ThrowNonClsCompliantException.il  
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs  
```  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1031: 일반적인 예외 형식을 catch하지 마십시오.](../code-quality/ca1031-do-not-catch-general-exception-types.md)  
  
## <a name="see-also"></a>참고 항목  
 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)   
 [Ilasm.exe(IL 어셈블러)](/dotnet/framework/tools/ilasm-exe-il-assembler)   
 [언어 독립성 및 언어 독립적 구성 요소](/dotnet/standard/language-independence-and-language-independent-components)