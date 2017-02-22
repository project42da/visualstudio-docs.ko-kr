---
title: "Attribute(XElement 동적 속성) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: 2
caps.handback.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Attribute(XElement 동적 속성)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 확장된 이름에 해당하는 특성 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## 구문  
  
```  
elem.Attribute[{namespaceName}attribName]  
```  
  
## 속성 값\/반환 값  
 `XAttribute Item(String expandedName)` 형식의 인덱서입니다.이 인덱서는 지정된 특성의 확장된 이름을 사용하여 해당하는 <xref:System.Xml.Linq.XAttribute>를 반환하거나 지정된 이름을 가진 특성이 없는 경우 `null`을 반환합니다.  
  
## 설명  
 이 속성은 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XElement.Attribute%2A> 메서드와 동일합니다.  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [XElement 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [값](../designers/value-xattribute-dynamic-property.md)