---
title: 'CA1050: 네임스페이스에 형식을 선언하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf38fde258a033fd4050e93d3ad69015f365dc60
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: 네임스페이스에 형식을 선언하십시오.
|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 명명된 된 네임 스페이스의 범위를 벗어나는 public 또는 protected 형식이 정의 됩니다.

## <a name="rule-description"></a>규칙 설명
 형식은 네임 스페이스 이름 충돌을 방지 하 고 관련 된 형식을 개체 계층을 구성 하는 방법으로 선언 됩니다. 명명된 된 네임 스페이스 외부에 있는 유형은 코드에서 참조할 수 없는 전역 네임 스페이스에서입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 네임 스페이스의 형식을 배치 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를에서 표시 하지 않으려면 필요, 없지만 어셈블리가 다른 어셈블리와 함께 사용 하지 않을 경우이 방법을 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 네임 스페이스, 외부 잘못 선언 형식이 지정 된 라이브러리와 이름이 같은 네임 스페이스 선언 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>예제
 다음 응용 프로그램은 이전에 정의 된 라이브러리를 사용 합니다. 네임 스페이스 외부 선언 된 형식을 생성 될 때 이름 `Test` 네임 스페이스로 한정 되지 않습니다. 액세스 하는 `Test` 에 입력 `Goodspace`, 네임 스페이스 이름은 필수입니다.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]