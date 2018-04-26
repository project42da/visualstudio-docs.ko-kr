---
title: 'CA2211: 비상수 필드는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b3c508aaf8632ff7fc064fabb4367044e079fa8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: 비상수 필드는 노출되면 안 됩니다.
|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|범주|Microsoft.Usage|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 정적 필드는 상수 나 읽기 전용입니다.

## <a name="rule-description"></a>규칙 설명
 상수도 아니고 읽기 전용도 아닌 정적 필드는 스레드로부터 안전하지 않습니다. 이러한 필드에 대 한 액세스는 신중 하 게 제어 해야 하며 클래스 개체에 대 한 액세스를 동기화 하기 위한 고급 프로그래밍 기술이 필요로 합니다. 어려운 기술은 배우기 이들은 이러한 개체를 테스트 그 자체로 위험 때문에 정적 필드는 저장 하는 데 변경 되지 않는 데이터입니다. 라이브러리;에이 규칙 적용 됩니다. 응용 프로그램에서 모든 필드를 노출 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 상수 또는 읽기 전용 정적 필드를 확인 합니다. 수 없는 경우에 스레드로부터 안전한 내부 필드에 대 한 액세스를 관리 하는 스레드로부터 안전한 속성과 같은 대체 메커니즘을 사용 하려면 형식이 다시 디자인 합니다. 참고로, 성능 및 라이브러리의 동작이 잠금 경합 및 교착 상태 등의 문제 달라질 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 응용 프로그램을 개발 하는 경우이 규칙에서 경고를 표시 하지 않고 있어서 정적 필드가 포함 된 형식의 액세스에 대해 모든 권한을 가지 안전 합니다. 라이브러리 디자이너;이 규칙에서 경고를 표시 해야 상수가 아닌 정적 필드를 사용 하 여 올바르게 사용 하려면 개발자 용 어려운 라이브러리를 사용 하 여 만들 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]