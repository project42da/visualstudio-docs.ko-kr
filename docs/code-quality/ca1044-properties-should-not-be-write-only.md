---
title: 'CA1044: 속성은 쓰기 전용이면 안 됩니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 204108ed86d37594d7debc0a69139a7f2a28a44a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: 속성은 쓰기 전용이면 안 됩니다.
|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 속성은 set 접근자가 없지만 get 접근자가 없습니다.

## <a name="rule-description"></a>규칙 설명
 Get 접근자는 속성에 대 한 읽기 액세스를 제공 및 set 접근자에는 쓰기 권한을 제공 합니다. 읽기 전용 속성을 사용하는 것은 가능하고 종종 필요하기도 하지만 쓰기 전용 속성의 사용은 금지되어 있습니다. 즉, 값을 설정 하는 사용자 하 고 값을 볼 수 없도록 때문에 사용자는 보안을 제공 하지 않습니다. 또한 읽기 권한이 없으면 공유 개체의 상태를 볼 수 없으므로 사용하는 데 제한을 받습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 속성에 get 접근자를 추가 합니다. 쓰기 전용 속성의 동작이 필요한 경우에이 속성을 메서드에 변환할 수도 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않는 것이 좋습니다.

## <a name="example"></a>예제
 다음 예에서 `BadClassWithWriteOnlyProperty` 쓰기 전용 속성을 가진 형식입니다. `GoodClassWithReadWriteProperty` 수정 된 코드를 포함합니다.

 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]