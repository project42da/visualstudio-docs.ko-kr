---
title: "CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1010"
  - "CollectionsShouldImplementGenericInterface"
helpviewer_keywords: 
  - "CA1010"
  - "CollectionsShouldImplementGenericInterface"
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 24
---
# CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CollectionsShouldImplementGenericInterface|  
|CheckId|CA1010|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 외부에 노출되는 형식이 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스는 구현하지만 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스는 구현하지 않으며, 포함하는 어셈블리가 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]을 대상으로 합니다.  이 규칙은 <xref:System.Collections.IDictionary?displayProperty=fullName>를 구현하는 형식을 무시합니다.  
  
## 규칙 설명  
 컬렉션의 유용성을 높이려면 제네릭 컬렉션 인터페이스 중 하나를 구현합니다.  그러면 컬렉션을 사용하여 다음과 같은 제네릭 컬렉션 형식을 채울 수 있습니다.  
  
-   <xref:System.Collections.Generic.List%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 다음 제네릭 컬렉션 인터페이스 중 하나를 구현합니다.  
  
-   <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.IList%601?displayProperty=fullName>  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시하지 않도록 설정해도 안전하지만 이렇게 하면 컬렉션의 용도가 더 제한됩니다.  
  
## 규칙 위반 예  
  
### 설명  
 다음 예제에서는 제네릭이 아닌 `CollectionBase` 클래스에서 파생되며 이 규칙을 위반하는 클래스\(참조 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]  
  
### 설명  
 이 규칙 위반 문제를 해결하려면 제네릭 인터페이스를 구현하거나 `Collection<T>` 클래스와 같이 제네릭 인터페이스와 제네릭이 아닌 인터페이스를 이미 모두 구현하는 형식으로 기본 형식을 변경해야 합니다.  
  
## 기본 형식 변경을 통한 해결 방법  
  
### 설명  
 다음 예제에서는 컬렉션의 기본 형식을 제네릭이 아닌 `CollectionBase` 클래스에서 제네릭 `Collection<T>`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Collection(Of T)`\) 클래스로 변경하여 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]  
  
### 설명  
 이미 발표된 클래스의 기본 클래스를 변경하는 것은 기존 소비자에게 주요 변경 사항으로 간주됩니다.  
  
## 인터페이스 구현을 통한 해결 방법  
  
### 설명  
 다음 예제에서는 제네릭 클래스 `IEnumerable<T>`, `ICollection<T>` 및 `IList<T>`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `IEnumerable(Of T)`, `ICollection(Of T)` 및 `IList(Of T)`\)를 구현하여 규칙 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]  
  
## 관련 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)