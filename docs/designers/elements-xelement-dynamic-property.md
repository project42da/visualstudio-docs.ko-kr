---
title: "Elements(XElement 동적 속성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
apiname: XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 24b28407d0b69d1ac7e2309ee1f8c24393b68e84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="elements-xelement-dynamic-property"></a>요소(XElement 동적 속성)
지정한 확장된 이름과 일치하는 현재 요소의 자식 요소를 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `IEnumerable<XElement> Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 원하는 자식 요소의 확장된 이름을 사용하여 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 컬렉션에서 일치하는 자식 요소를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XContainer> 메서드와 동일합니다.  
  
 반환된 컬렉션의 요소는 XML 소스 문서 순서로 되어 있습니다.  
  
 이 속성은 지연된 실행을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [요소](../designers/element-xelement-dynamic-property.md)   
 [하위 항목](../designers/descendants-xelement-dynamic-property.md)