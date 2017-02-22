---
title: "CA1039: 목록은 강력한 형식이어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1039"
  - "ListsAreStronglyTyped"
helpviewer_keywords: 
  - "CA1039"
  - "ListsAreStronglyTyped"
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1039: 목록은 강력한 형식이어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ListsAreStronglyTyped|  
|CheckId|CA1039|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 <xref:System.Collections.IList?displayProperty=fullName>를 구현하지만 다음 중 하나 이상에 대해 강력한 형식의 메서드를 제공하지 않습니다.  
  
-   IList.Item  
  
-   IList.Add  
  
-   IList.Contains  
  
-   IList.IndexOf  
  
-   IList.Insert  
  
-   IList.Remove  
  
## 규칙 설명  
 이 규칙에서는 사용자가 인터페이스에서 제공하는 기능을 사용할 때 인수를 <xref:System.Object> 형식으로 캐스팅할 필요가 없도록 <xref:System.Collections.IList?displayProperty=fullName> 구현에서 강력한 형식의 멤버를 제공할 것을 요구합니다.  <xref:System.Collections.IList> 인터페이스는 인덱스로 액세스할 수 있는 개체 컬렉션으로 구현됩니다.  이 규칙에서는 <xref:System.Collections.IList>를 구현하는 형식이 이를 수행하여 <xref:System.Object>보다 강력한 형식의 인스턴스 컬렉션을 관리한다고 가정합니다.  
  
 <xref:System.Collections.IList>는 <xref:System.Collections.ICollection?displayProperty=fullName> 및 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현합니다.  <xref:System.Collections.IList>를 구현하는 경우 <xref:System.Collections.ICollection>에 필수적인 강력한 형식의 멤버를 제공해야 합니다.  컬렉션의 개체가 <xref:System.ValueType?displayProperty=fullName>을 확장하는 경우 <xref:System.Collections.IEnumerable.GetEnumerator%2A>에 대한 강력한 형식의 멤버를 제공하여 boxing으로 인한 성능 저하를 막아야 합니다. 컬렉션의 개체가 참조 형식인 경우에는 이렇게 할 필요가 없습니다.  
  
 이 규칙을 준수하려면 <xref:System.Collections.IList.Add%2A>와 같이 InterfaceName.InterfaceMemberName 형태의 이름을 사용하여 인터페이스 멤버를 명시적으로 구현합니다.  명시적인 인터페이스 멤버는 인터페이스에 선언된 데이터 형식을 사용합니다.  `Add` 같이 인터페이스 멤버 이름을 사용하여 강력한 형식의 멤버를 구현합니다.  강력한 형식의 멤버를 public으로 선언하고 매개 변수 및 반환 값을 컬렉션에서 관리되는 강력한 형식으로 선언합니다.  인터페이스에 선언된 <xref:System.Object> 및 <xref:System.Array> 등의 더 약한 형식이 강력한 형식으로 바뀝니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Collections.IList> 멤버를 명시적으로 구현하고 앞서 언급한 멤버에 강력한 형식의 멤버를 제공합니다.  다음 예제에서 <xref:System.Collections.IList> 인터페이스를 올바르게 구현하고 필수적인 강력한 형식의 멤버를 제공하는 코드를 볼 수 있습니다.  
  
## 경고를 표시하지 않는 경우  
 연결된 목록 같이 새 컬렉션을 확장하는 형식이 강력한 형식을 결정하는 새로운 개체 기반 컬렉션을 구현할 경우에는 이 규칙에서 경고를 표시하지 않습니다.  이러한 형식은 이 규칙을 따라야 하며 강력한 형식의 멤버를 노출해야 합니다.  
  
## 예제  
 다음 예제에서 `YourType` 형식은 모든 강력한 형식의 컬렉션에서처럼 <xref:System.Collections.CollectionBase?displayProperty=fullName>를 확장합니다.  <xref:System.Collections.CollectionBase>는 <xref:System.Collections.IList> 인터페이스의 명시적 구현을 제공합니다.  따라서 <xref:System.Collections.IList> 및 <xref:System.Collections.ICollection>에 대해서 강력한 형식의 멤버만 제공해야 합니다.  
  
 [!code-cs[FxCop.Design.IListStrongTypes#1](../code-quality/codesnippet/CSharp/ca1039-lists-are-strongly-typed_1.cs)]  
  
## 관련 규칙  
 [CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1038: 열거자는 강력한 형식이어야 합니다.](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)  
  
## 참고 항목  
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.ICollection?displayProperty=fullName>   
 <xref:System.Collections.IEnumerable?displayProperty=fullName>   
 <xref:System.Collections.IList?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>