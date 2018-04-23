---
title: 'CA2120: serialization 생성자를 안전하게 하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06d6dd2bab5bf47b4e384c6d260cda4221155fde
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: serialization 생성자를 안전하게 하십시오.
|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스, 대리자 또는 인터페이스를 아니며 부분적으로 신뢰할 수 있는 호출자를 허용 하는 어셈블리에서 선언 됩니다. 형식에 사용 하는 생성자는 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> 개체 및 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 개체 (serialization 생성자 시그니처). 이 생성자는 보안 검사를 통해 보안 되지 않지만 하나 이상의 정규 생성자 형식에 보안이 설정 됩니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 사용자 지정 serialization을 지 원하는 형식과 관련이 있습니다. 구현 하는 경우 원하는 사용자 지정 직렬화를 한 종류의 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스입니다. Serialization 생성자를 사용 하는 필수 항목이 며 역직렬화 할 시키거나 다시 사용 하 여 serialize 된 개체를 만드는 데 사용 되는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드. Serialization 생성자를 할당 개체를 초기화 하므로, 정규 생성자에 있는 보안 검사도 serialization 생성자에 제공 되어야 합니다. 이 규칙을 위반 하는 경우 그렇지 않은 경우 인스턴스를 만들지 못했습니다 호출자 이렇게 하려면 serialization 생성자를 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 다른 생성자를 보호 하는 동일한 보안 요청으로 serialization 생성자를 보호 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 규칙의 위반을 표시 하지 마십시오.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>