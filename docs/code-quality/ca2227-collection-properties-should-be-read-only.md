---
title: "CA2227: 컬렉션 속성은 읽기 전용이어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2227"
  - "CollectionPropertiesShouldBeReadOnly"
helpviewer_keywords: 
  - "CA2227"
  - "CollectionPropertiesShouldBeReadOnly"
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CollectionPropertiesShouldBeReadOnly|  
|CheckId|CA2227|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 쓰기 가능한 속성이 <xref:System.Collections.ICollection?displayProperty=fullName>을 구현하는 형식입니다.  배열, 인덱서\(이름이 'Item'인 속성\) 및 권한 집합은 이 규칙에서 무시됩니다.  
  
## 규칙 설명  
 쓰기 가능한 컬렉션 속성으로 사용자는 컬렉션을 전혀 다른 컬렉션으로 바꿀 수 있습니다.  읽기 전용 속성은 컬렉션을 바꾸지 못하도록 하지만 개별 멤버를 설정하는 것은 여전히 가능합니다.  컬렉션을 바꾸려는 경우에 많이 사용하는 디자인 패턴은 컬렉션에서 모든 요소를 제거하는 메서드와 컬렉션을 다시 채우는 메서드를 포함시키는 것입니다.  이 패턴의 예제를 보려면 <xref:System.Collections.ArrayList?displayProperty=fullName> 클래스의 <xref:System.Collections.ArrayList.Clear%2A> 및 <xref:System.Collections.ArrayList.AddRange%2A> 메서드를 참조하십시오.  
  
 이진 및 XML serialization에서는 컬렉션인 읽기 전용 속성을 지원합니다.  <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 클래스에는 <xref:System.Collections.ICollection> 및 <xref:System.Collections.IEnumerable?displayProperty=fullName>을 구현하는 형식이 serialize가 가능하도록 하기 위한 특정 요구 사항이 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 속성을 읽기 전용으로 만들고 디자인에 필요한 경우 컬렉션을 지우고 다시 채우는 메서드를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 쓰기 가능한 컬렉션 속성이 있는 형식을 보여 주고 컬렉션을 직접 바꾸는 방법을 보여 줍니다.  또한 `Clear` 및 `AddRange` 메서드를 사용하여 읽기 전용 컬렉션 속성을 바꾸는 방법도 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]  
  
## 관련 규칙  
 [CA1819: 속성은 배열을 반환해서는 안 됩니다.](../code-quality/ca1819-properties-should-not-return-arrays.md)