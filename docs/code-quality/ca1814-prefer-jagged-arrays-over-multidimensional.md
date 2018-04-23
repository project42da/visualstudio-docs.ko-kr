---
title: 'CA1814: 다차원 배열보다 가변 배열을 사용하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cedac542d003ccc89357f3a01e2f167a2471a128
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: 다차원 배열보다 가변 배열을 사용하십시오.
|||
|-|-|
|TypeName|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|범주|Microsoft.Performance|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 멤버는 다차원 배열로 선언 됩니다.

## <a name="rule-description"></a>규칙 설명
 가변 배열의 요소에는 배열이 사용됩니다. 요소를 구성하는 배열의 크기는 서로 다를 수 있습니다. 이 경우 일부 데이터 집합에 대한 공간을 절약할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 가변된 배열을 다차원 배열을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 다차원 배열 공간 허비 되지 않도록 하는 경우에이 규칙에서 경고를 표시 합니다.

## <a name="example"></a>예제
 다음 예제에는 가변 및 다차원 배열에 대 한 선언을 보여 줍니다.

 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]