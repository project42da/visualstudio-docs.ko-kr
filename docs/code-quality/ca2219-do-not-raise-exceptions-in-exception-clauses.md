---
title: 'CA2219: exception 절에서 예외를 발생시키지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d90e56eee9c68ff94b18204928ecaeeeb55ae0a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: exception 절에서 예외를 발생시키지 마십시오.
|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 예외가 throw 되는 `finally`, 필터 또는 fault 절.

## <a name="rule-description"></a>규칙 설명
 Exception 절에서 예외가 발생 하면 디버깅의 어려움 크게 증가 합니다.

 예외가 발생 한 경우는 `finally` 또는 fault 절 하면 새로운 예외가 활성 예외를 숨기 있는 경우. 따라서 원래 오류를 감지 하 여 디버그 어렵게 합니다.

 필터 절에서 예외가 발생 하면 런타임에서 자동으로 예외를 catch 하 고 하면 필터가 평가 결과가 false입니다. 필터에서 throw 하는 예외를 false로 계산 되는 필터의 차이 확인할 수가 있습니다. 따라서 검색 및 필터 논리의 오류를 디버그 어려운 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반이를 해결 하려면 명시적으로 올리지 마십시오에서 예외는 `finally`, 필터 또는 fault 절.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에 대 한 경고를 표시 하지 마십시오. 되 exception 절에서 발생 한 예외는 실행 중인 코드에 도움이 시나리오가 있습니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1065: 예기치 않은 위치에서 예외를 발생시키지 마십시오.](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>참고 항목
 [디자인 경고](../code-quality/design-warnings.md)