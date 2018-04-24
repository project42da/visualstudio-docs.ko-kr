---
title: Value(XAttribute 동적 속성)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b98272fe2c86137eb925a54924e1b0e8411ed0e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="value-xattribute-dynamic-property"></a>Value(XAttribute 동적 속성)

XML 특성의 값을 가져오거나 설정합니다.

## <a name="syntax"></a>구문

```
attrib.Value
```

## <a name="property-valuereturn-value"></a>속성 값/반환 값

이 특성의 값을 포함하는 <xref:System.String>

## <a name="exceptions"></a>예외

|예외 형식|조건|
|--------------------|---------------|
|<xref:System.ArgumentNullException>|설정할 때 `value`가 `null`인 경우|

## <a name="remarks"></a>설명

이 속성은 <xref:System.Xml.Linq.XAttribute.Value%2A> 클래스의 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 속성과 동일하지만 이 동적 속성은 변경 알림도 지원합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute 클래스 동적 속성](../designers/xattribute-class-dynamic-properties.md)
- [특성](../designers/attribute-xelement-dynamic-property.md)