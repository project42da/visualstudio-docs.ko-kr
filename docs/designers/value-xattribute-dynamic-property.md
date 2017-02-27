---
title: "Value(XAttribute 동적 속성) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "XAttribute.Value"
apitype: "Assembly"
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# Value(XAttribute 동적 속성)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

XML 특성의 값을 가져오거나 설정합니다.  
  
## 구문  
  
```  
attrib.Value   
```  
  
## 속성 값\/반환 값  
 이 특성의 값을 포함하는 <xref:System.String>  
  
## 예외  
  
|예외 형식|조건|  
|-----------|--------|  
|<xref:System.ArgumentNullException>|설정할 때 `value`가 `null`인 경우|  
  
## 설명  
 이 속성은 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성과 동일하지만 이 동적 속성은 변경 알림도 지원합니다.  
  
## 참고 항목  
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [XAttribute 클래스 동적 속성](../designers/xattribute-class-dynamic-properties.md)   
 [특성](../designers/attribute-xelement-dynamic-property.md)