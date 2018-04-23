---
title: 'CA2229: serialization 생성자를 구현하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d116c77aa01e9b22da3e2037f29deb1b8c47e64c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: serialization 생성자를 구현하십시오.
|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스, 대리자 또는 인터페이스를 않습니다 및 다음 조건 중 하나에:

-   형식을 사용 하는 생성자가 없습니다는 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> 개체 및 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 개체 (serialization 생성자 시그니처).

-   형식이 봉인 하 고 해당 serialization 생성자에 대 한 액세스 한정자는 보호 된 (제품군) 되지 않습니다.

-   형식이 sealed 및 serialization 생성자에 대 한 액세스 한정자가 private입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 사용자 지정 serialization을 지 원하는 형식과 관련이 있습니다. 구현 하는 경우 원하는 사용자 지정 직렬화를 한 종류의 <xref:System.Runtime.Serialization.ISerializable> 인터페이스입니다. Serialization 생성자를 deserialize를 만들거나 다시 사용 하 여 serialize 된 개체를 만드는 데 필요한는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다. 봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 규칙의 위반을 표시 하지 마십시오. 유형을은 역직렬화 할 수, 되지 않으며 대부분의 시나리오에서 작동 하지 않습니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 충족 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>