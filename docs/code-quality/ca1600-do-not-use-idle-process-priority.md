---
title: 'CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3dcac11312b15049c743d596914b06819000801
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.
|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|범주|Microsoft.Mobility|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 이 규칙은 프로세스로 설정 된 경우 `ProcessPriorityClass.Idle`합니다.

## <a name="rule-description"></a>규칙 설명
 프로세스 우선 순위를 유휴 상태로 설정하지 마십시오. 프로세스에 `System.Diagnostics.ProcessPriorityClass.Idle` 유휴, 블록이 대기 경우 CPU를 차지 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 프로세스 설정 `ProcessPriorityClass.BelowNormal`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 유휴 상태 프로세스 우선 순위 필수 이며 이동성 고려 사항의 안전 하 게 무시할 수 있습니다. 경우에이 규칙을 표시 해야 합니다.