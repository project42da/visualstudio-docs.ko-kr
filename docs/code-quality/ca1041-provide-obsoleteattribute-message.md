---
title: 'CA1041: ObsoleteAttribute 메시지를 제공하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7ac873aa7a6a86e2c4fe9964d0b690950aa0fb9e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute 메시지를 제공하십시오.
|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식 또는 멤버를 사용 하 여 표시 되는 <xref:System.ObsoleteAttribute?displayProperty=fullName> 하지 않은 특성의 <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> 지정 된 속성입니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.ObsoleteAttribute> 사용 되지 않는 라이브러리 형식 및 멤버를 표시 하는 데 사용 됩니다. 라이브러리 소비자에 임의의 유형 또는 사용 되지 않는 표시 된 멤버의 사용을 피해 야 합니다. 지원 되지 않는 하 고 결국 라이브러리의 이후 버전에서 제거 될 때문입니다. 형식 또는 멤버를 사용 하 여 표시 하는 경우 <xref:System.ObsoleteAttribute> 컴파일되는 경우는 <xref:System.ObsoleteAttribute.Message%2A> 특성의 속성이 표시 됩니다. 사용되지 않는 형식 또는 멤버에 대한 정보가 사용자에게 제공됩니다. 이 정보에는 일반적으로 사용 되지 않는 형식을 얼마나 포함 또는 라이브러리 디자이너 정보와 대신 사용 하 여 멤버를 지원 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 추가 `message` 매개 변수는 <xref:System.ObsoleteAttribute> 생성자입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 때문에이 규칙에서는 경고를에서 표시 해야는 <xref:System.ObsoleteAttribute.Message%2A> 속성은 사용 되지 않는 형식 또는 멤버에 대 한 중요 한 정보를 제공 합니다.

## <a name="example"></a>예제
 다음 예제는 사용 되지 않는 가진 멤버를 올바르게 선언 된 <xref:System.ObsoleteAttribute>합니다.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>참고 항목
 <xref:System.ObsoleteAttribute?displayProperty=fullName>