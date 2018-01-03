---
title: "Attribute(XElement 동적 속성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e3f373f4732aa80ac0e72f044e7a6a7f08e8a9be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="attribute-xelement-dynamic-property"></a>특성(XElement 동적 속성)
지정한 확장된 이름에 해당하는 특성 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
elem.Attribute[{namespaceName}attribName]  
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `XAttribute Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 지정된 특성의 확장된 이름을 사용하여 해당하는 <xref:System.Xml.Linq.XAttribute>를 반환하거나 지정된 이름을 가진 특성이 없는 경우 `null`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 <xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 메서드와 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [Value](../designers/value-xattribute-dynamic-property.md)