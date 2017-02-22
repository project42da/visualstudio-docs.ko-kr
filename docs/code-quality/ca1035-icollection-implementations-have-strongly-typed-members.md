---
title: "CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다. | Microsoft Docs"
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
  - "ICollectionImplementationsHaveStronglyTypedMembers"
  - "CA1035"
helpviewer_keywords: 
  - "CA1035"
  - "ICollectionImplementationsHaveStronglyTypedMembers"
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|  
|CheckId|CA1035|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 <xref:System.Collections.ICollection?displayProperty=fullName>을 구현하지만 <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>에 강력한 형식의 메서드를 제공하지 않습니다.  <xref:System.Collections.ICollection.CopyTo%2A>의 강력한 형식 버전에서는 매개 변수 두 개를 받아들여야 하며 <xref:System.Array?displayProperty=fullName> 또는 <xref:System.Object?displayProperty=fullName>의 배열을 첫 번째 매개 변수로 사용할 수 없습니다.  
  
## 규칙 설명  
 이 규칙에서는 사용자가 인터페이스에서 제공하는 기능을 사용할 때 인수를 <xref:System.Object> 형식으로 캐스팅할 필요가 없도록 <xref:System.Collections.ICollection> 구현에서 강력한 형식의 멤버를 제공할 것을 요구합니다.  이 규칙에서는 <xref:System.Collections.ICollection>을 구현하는 형식이 이를 수행하여 <xref:System.Object>보다 강력한 형식의 인스턴스 컬렉션을 관리한다고 가정합니다.  
  
 <xref:System.Collections.ICollection>는 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현합니다.  컬렉션의 개체가 <xref:System.ValueType?displayProperty=fullName>을 확장하는 경우 <xref:System.Collections.IEnumerable.GetEnumerator%2A>에 대한 강력한 형식의 멤버를 제공하여 boxing으로 인한 성능 저하를 막아야 합니다.  컬렉션의 개체가 참조 형식인 경우에는 필요하지 않습니다.  
  
 인터페이스 멤버의 강력한 형식 버전을 구현하려면 <xref:System.Collections.ICollection.CopyTo%2A> 같이 `InterfaceName.InterfaceMemberName` 형태의 이름을 사용하여 인터페이스 멤버를 명시적으로 구현합니다.  명시적인 인터페이스 멤버는 인터페이스에 선언된 데이터 형식을 사용합니다.  <xref:System.Collections.ICollection.CopyTo%2A> 같이 인터페이스 멤버 이름을 사용하여 강력한 형식의 멤버를 구현합니다.  강력한 형식의 멤버를 public으로 선언하고 매개 변수 및 반환 값을 컬렉션에서 관리되는 강력한 형식으로 선언합니다.  인터페이스에 선언된 <xref:System.Object> 및 <xref:System.Array> 등의 더 약한 형식이 강력한 형식으로 바뀝니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 인터페이스 멤버를 <xref:System.Collections.ICollection.CopyTo%2A>로 선언하여 명시적으로 구현합니다.  `CopyTo`로 선언된 강력한 형식의 public 멤버를 추가하고 강력한 형식의 배열을 첫 번째 매개 변수로 사용하도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 이진 트리 같이 새 컬렉션을 확장하는 형식이 강력한 형식을 결정하는 새로운 개체 기반 컬렉션을 구현할 경우에는 이 규칙에서 경고를 표시하지 않습니다.  이러한 형식은 이 규칙을 따라야 하며 강력한 형식의 멤버를 노출해야 합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Collections.ICollection>을 구현하는 올바른 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]  
  
## 관련 규칙  
 [CA1038: 열거자는 강력한 형식이어야 합니다.](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)  
  
 [CA1039: 목록은 강력한 형식이어야 합니다.](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## 참고 항목  
 <xref:System.Array?displayProperty=fullName>   
 <xref:System.Collections.IEnumerable?displayProperty=fullName>   
 <xref:System.Collections.ICollection?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>