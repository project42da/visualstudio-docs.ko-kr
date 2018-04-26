---
title: 요소(XElement 동적 속성)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4100e26d07b9dc76f9947e4f5a5f7db3a901abe2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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

- [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)
- [요소](../designers/element-xelement-dynamic-property.md)
- [하위 항목](../designers/descendants-xelement-dynamic-property.md)