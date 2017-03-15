---
title: "CA1007: 적합한 제네릭을 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1007"
  - "UseGenericsWhereAppropriate"
helpviewer_keywords: 
  - "CA1007"
  - "UseGenericsWhereAppropriate"
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA1007: 적합한 제네릭을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseGenericsWhereAppropriate|  
|CheckId|CA1007|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 메서드에 <xref:System.Object?displayProperty=fullName> 형식의 참조 매개 변수가 포함되어 있으며 포함하는 어셈블리가 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]을 대상으로 합니다.  
  
## 규칙 설명  
 참조 매개 변수는 `ref`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `ByRef`\) 키워드를 사용하여 수정되는 매개 변수입니다.  참조 매개 변수에 제공되는 인수 형식은 참조 매개 변수 형식과 정확하게 일치해야 합니다.  참조 매개 변수 형식에서 파생된 형식을 사용하려면 먼저 형식을 캐스팅하고 참조 매개 변수 형식의 변수에 할당해야 합니다.  제네릭 메서드를 사용하면 제약 조건에 따라 형식을 참조 매개 변수 형식으로 먼저 캐스팅하지 않고도 모든 형식을 메서드에 전달할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 제네릭으로 만들고 <xref:System.Object> 매개 변수를 형식 매개 변수를 사용하여 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 제네릭이 아닌 메서드와 제네릭 메서드 모두로 구현되는 범용 스왑 루틴을 보여 줍니다.  제네릭 메서드를 사용할 경우 제네릭이 아닌 메서드에 비해 문자열을 효과적으로 바꿀 수 있음을 알 수 있습니다.  
  
 [!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
 [!code-cs[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]  
  
## 관련 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)