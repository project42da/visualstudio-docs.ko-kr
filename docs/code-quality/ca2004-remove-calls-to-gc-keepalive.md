---
title: 'CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa59c6797d81202637f44799327e6b2802d822eb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.
|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 사용 하는 클래스 `SafeHandle` 여전히에 대 한 호출을 포함 하지만 `GC.KeepAlive`합니다.

## <a name="rule-description"></a>규칙 설명
 변환 하는 경우 `SafeHandle` 사용에 대 한 모든 호출을 제거 `GC.KeepAlive` (개체). 이 경우 클래스 필요가 없습니다 호출 `GC.KeepAlive`, 종료자 필요는 없지만 사용 될 것으로 가정 `SafeHandle` OS 핸들 완성 합니다.  하지만 비용에 대 한 호출의 끝낼 `GC.KeepAlive` 말하는 성능을 기준으로 무시할 수 없습니다는에 대 한 호출 `GC.KeepAlive` 필요 하거나 더 이상 존재 하는 문제는 코드를 하기 어렵게 만듭니다 수명 해결 하기 위해 충분 한 유지 관리 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 에 대 한 호출을 제거 `GC.KeepAlive`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 기술적으로 잘못 변환할 경우에이 경고를 표시 하지 않을 수 `SafeHandle` 클래스에서 사용 합니다.