---
title: "Element(XElement 동적 속성) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "XElement.Element"
apitype: "Assembly"
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
caps.latest.revision: 2
caps.handback.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Element(XElement 동적 속성)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 확장된 이름에 해당하는 자식 요소 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## 구문  
  
```  
elem.Element[{namespaceName}localName]  
```  
  
## 속성 값\/반환 값  
 `XElement Item(String expandedName)` 형식의 인덱서입니다.이 인덱서는 확장된 이름 매개 변수를 사용하여 해당하는 <xref:System.Xml.Linq.XElement>를 반환하거나, 지정된 이름을 가진 요소가 없는 경우 `null`을 반환합니다.  
  
## 설명  
 이 속성은 <xref:System.Xml.Linq.XContainer?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드와 동일합니다.  
  
## 참고 항목  
 <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>   
 [XElement 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [요소](../designers/elements-xelement-dynamic-property.md)