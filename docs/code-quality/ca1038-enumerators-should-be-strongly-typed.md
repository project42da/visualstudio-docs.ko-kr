---
title: "CA1038: 열거자는 강력한 형식이어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EnumeratorsShouldBeStronglyTyped"
  - "CA1038"
helpviewer_keywords: 
  - "CA1038"
  - "EnumeratorsShouldBeStronglyTyped"
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 16
---
# CA1038: 열거자는 강력한 형식이어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|EnumeratorsShouldBeStronglyTyped|  
|CheckId|CA1038|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 <xref:System.Collections.IEnumerator?displayProperty=fullName>를 구현하지만 <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> 속성의 강력한 형식 버전을 제공하지 않습니다.  다음 형식에서 파생된 형식은 이 규칙에서 예외입니다.  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
## 규칙 설명  
 이 규칙에서는 <xref:System.Collections.IEnumerator> 구현에서 <xref:System.Collections.IEnumerator.Current%2A> 속성의 강력한 형식 버전도 제공하도록 하여 사용자가 인터페이스에서 제공하는 기능을 사용할 때 반환 값을 강력한 형식으로 캐스팅할 필요가 없도록 합니다.  이 규칙에서는 <xref:System.Collections.IEnumerator>를 구현하는 형식에 <xref:System.Object>보다 강력한 형식의 인스턴스 컬렉션이 들어 있다고 가정합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 인터페이스 속성을 `IEnumerator.Current`로 선언하여 명시적으로 구현합니다.  `Current`로 선언된, 속성에 대한 강력한 형식의 public 버전을 추가하고 강력한 형식의 개체를 반환하도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 이진 트리와 같은 개체 기반 컬렉션에서 사용할 개체 기반 열거자를 구현할 때는 이 규칙에 따른 경로를 표시하지 마십시오.  새 컬렉션을 확장하는 형식은 강력한 형식의 열거자를 정의하고 강력한 형식의 속성을 노출합니다.  
  
## 예제  
 다음 예제에서는 강력한 형식의 <xref:System.Collections.IEnumerator> 형식을 구현하는 올바른 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]  
  
## 관련 규칙  
 [CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1039: 목록은 강력한 형식이어야 합니다.](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## 참고 항목  
 <xref:System.Collections.IEnumerator?displayProperty=fullName>   
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.DictionaryBase?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>