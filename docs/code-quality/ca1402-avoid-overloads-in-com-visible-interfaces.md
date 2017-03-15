---
title: "CA1402: COM 노출 인터페이스에서 오버로드를 사용하지 마십시오. | Microsoft Docs"
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
  - "AvoidOverloadsInComVisibleInterfaces"
  - "CA1402"
helpviewer_keywords: 
  - "AvoidOverloadsInComVisibleInterfaces"
  - "CA1402"
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1402: COM 노출 인터페이스에서 오버로드를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidOverloadsInComVisibleInterfaces|  
|CheckId|CA1402|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 COM\(Component Object Model\) 노출 인터페이스는 오버로드된 메서드를 선언합니다.  
  
## 규칙 설명  
 오버로드된 메서드가 COM 클라이언트에 노출되면 첫 번째 메서드 오버로드만 이름이 유지됩니다.  이후의 오버로드는 이름에 밑줄 문자 '\_'와 오버로드 선언 순서에 해당하는 정수가 추가되어 고유한 이름이 지정됩니다.  예를 들어, 다음 메서드를 확인해 보십시오.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod(int valueOne, int valueTwo, int valueThree);  
void SomeMethod(int valueOne, int valueTwo);  
```  
  
 이러한 메서드는 COM 클라이언트에 다음과 같이 노출됩니다.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);  
void SomeMethod_3(int valueOne, int valueTwo);  
```  
  
 Visual Basic 6 COM 클라이언트는 이름에 밑줄이 있는 인터페이스 메서드를 구현할 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 오버로드된 메서드의 이름을 고유한 이름으로 바꿉니다.  또는 액세스 가능성을 `internal`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Friend`\)로 변경하거나 `false`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 특성을 적용하여 COM에서 인터페이스를 볼 수 없도록 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 인터페이스와 규칙을 충족하는 인터페이스를 보여 줍니다.  
  
 [!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
 [!code-cs[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]  
  
## 관련 규칙  
 [CA1413: ComVisible 값 형식에 public이 아닌 필드를 사용하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](../Topic/CA1407:%20Avoid%20static%20members%20in%20COM%20visible%20types.md)  
  
 [CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Long Data Type](/dotnet/visual-basic/language-reference/data-types/long-data-type)