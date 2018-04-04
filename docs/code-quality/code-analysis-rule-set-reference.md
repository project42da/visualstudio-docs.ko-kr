---
title: 코드 분석 규칙 집합 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0bc2b01641c6f6b333ef5323a60672818cc5e7b3
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="code-analysis-rule-set-reference"></a>코드 분석 규칙 집합 참조

기본 제공 목록으로 표시 된 Visual Studio에서 관리 되는 코드 프로젝트에 대 한 코드 분석을 구성할 때 *규칙 집합*합니다. 표준 규칙 집합 중 하나를 사용 하거나 또는 규칙 집합을 프로젝트 요구 사항에 맞게 사용자 지정할 수 있습니다.

## <a name="available-rule-sets"></a>사용 가능한 규칙 집합

다음 표에는 기본 규칙 집합이 나열됩니다.

|||
|-|-|
|[모든 규칙 규칙 집합](../code-quality/all-rules-rule-set.md)|이 규칙 집합에 있는 모든 규칙을 포함합니다. 이 규칙 집합 실행 되 고 보고 된 경고 수가 많은 발생할 수 있습니다. 이 규칙 집합 프로그램 코드에서 얻을 수 있는 모든 문제의 포괄적인 그림을 사용 합니다. 이 집합은 가장 적합 한 프로젝트에 대해 실행 하는 더욱 중점 둔된 규칙을 결정 하는 데 수 있습니다.|
|[관리 코드에 대한 기본 수정 규칙 규칙 집합](../code-quality/basic-correctness-rules-rule-set-for-managed-code.md)|이러한 규칙은 논리 오류 및 일반적인 실수 프레임 워크 Api 사용에 초점을 둡니다. 이 규칙 집합의 최소 권장된 규칙에 의해 보고 된 경고 목록에 확장을 포함 합니다.|
|[관리 코드에 대한 기본 디자인 지침 규칙 규칙 집합](../code-quality/basic-design-guideline-rules-rule-set-for-managed-code.md)|이러한 규칙 코드를 더 쉽게 이해 하 고 모범 사례를 적용에 집중 합니다. 프로젝트에 라이브러리 코드가 있거나 유지 관리를 쉽게 코드에 대 한 모범 사례를 적용 하려는 경우이 규칙 집합을 포함 합니다.|
|[관리 코드에 대한 확장 수정 규칙 규칙 집합](../code-quality/extended-correctness-rules-rule-set-for-managed-code.md)|이러한 규칙은 기본 수정 규칙을 보고 되는 논리 및 프레임 워크 사용 오류를 최대화 하기 위해 확장 합니다. COM interop 및 모바일 응용 프로그램 같은 특정 시나리오에 주안점을 둡니다. 이러한 시나리오 중 하나가 적용 프로젝트 또는 프로젝트의 추가 문제를 찾을 경우이 규칙 집합을 포함 하는 것이 좋습니다.|
|[관리 코드에 대한 확장 디자인 지침 규칙 규칙 집합](../code-quality/extended-design-guidelines-rules-rule-set-for-managed-code.md)|이러한 규칙은 보고 되는 유용성 및 유지 관리 문제를 최대화 하기 위해 기본 디자인 지침 규칙에서 확장 됩니다. 명명 지침에 주안점을 둡니다. 프로젝트에 라이브러리 코드가 있거나 유지 관리 가능한 코드를 작성 하기 위한 가장 높은 표준을 적용 하려는 경우이 규칙 집합을 포함 하는 것이 좋습니다.|
|[관리 코드에 대한 전역화 규칙 규칙 집합](../code-quality/globalization-rules-rule-set-for-managed-code.md)|이러한 규칙 다양 한 언어, 로캘 및 문화권에서 사용 될 때 올바로 표시 응용 프로그램에서 데이터를 방해 하는 문제에 초점을 맞춥니다. 응용 프로그램이 지역화 되거나 전역화 되는 경우이 규칙 집합을 포함 합니다.|
|[관리 코드에 대 한 설정 관리 최소 규칙 규칙](../code-quality/managed-minimun-rules-rule-set-for-managed-code.md)|이러한 규칙은 코드 분석은 가장 정확한 코드의 가장 중요 한 문제에 집중 합니다. 이러한 규칙은 수가 적으며 하 고만 제한 된 버전의 Visual Studio에서 실행 하는 것은 키를 누릅니다. 다른 Visual Studio 버전 MinimumRecommendedRules.ruleset을 사용 합니다.|
|[관리 코드에 대한 관리 권장 규칙 규칙 집합](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md)|이러한 규칙은 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요 한 논리 및 디자인 오류를 비롯 하 여 코드의 가장 중요 한 문제에 집중 합니다. 프로젝트에 대해 만드는이 규칙 사용자 지정 규칙 집합에 있는 집합을 포함 해야 합니다.|
|[혼합 최소 규칙 규칙 집합](../code-quality/mixed-minimum-rules-rule-set.md)|이러한 규칙을 지 원하는 잠재적 보안 허점 및 응용 프로그램 충돌을 포함 하 여 공용 언어 런타임 c + + 프로젝트에서 가장 중요 한 문제에 초점을 맞춥니다. 공용 언어 런타임을 지 원하는 c + + 프로젝트에 대해 만드는이 규칙 사용자 지정 규칙 집합에 있는 집합을 포함 해야 합니다.|
|[혼합 권장 규칙 규칙 집합](../code-quality/mixed-recommended-rules-rule-set.md)|이러한 규칙을 지 원하는 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요 한 논리 및 디자인 오류를 포함 하 여 공용 언어 런타임 c + + 프로젝트에서 가장 일반적이 고 중요 한 문제에 초점을 맞춥니다. 공용 언어 런타임을 지 원하는 c + + 프로젝트에 대해 만드는이 규칙 사용자 지정 규칙 집합에 있는 집합을 포함 해야 합니다. |
|[네이티브 최소 규칙 규칙 집합](../code-quality/native-minimum-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점 및 응용 프로그램 충돌을 비롯 하 여 네이티브 코드의 가장 중요 한 문제에 집중 합니다. 네이티브 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.|
|[네이티브 권장 규칙 규칙 집합](../code-quality/native-recommended-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점 및 응용 프로그램 충돌을 비롯 하 여 네이티브 코드의 가장 중요 하 고 일반적인 문제에 집중 합니다. 네이티브 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다. |
|[관리 코드에 대한 보안 규칙 규칙 집합](../code-quality/security-rules-rule-set-for-managed-code.md)|이 규칙 집합에는 모든 Microsoft 보안 규칙이 포함 되어 있습니다. 이 규칙을 보고 되는 잠재적 보안 문제의 수를 최대화 하기 위해 집합을 포함 합니다.|
