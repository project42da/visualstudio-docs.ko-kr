---
title: "방법: 코드 분석 체크 인 정책 사용 하 여 유지 관리 가능한 코드를 적용 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7b1a6d953128317e89672d5d9b175ce7acc1b63f
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>방법: 코드 분석 체크 인 정책 사용 하 여 유지 관리 가능한 코드 적용

개발자 코드 메트릭 도구를 사용 하 여 복잡성 및 코드의 유지 관리 용이성 측정 하도록 하지만 체크 인 정책의 일부로 코드 메트릭을 호출할 수 없습니다. 그러나 코드 메트릭 표준 코드의 준수를 확인 하는 코드 분석 규칙 고 체크 인 정책을 통해 규칙을 적용할 수 있습니다. 코드 메트릭에 대 한 자세한 내용은 참조 [코드 메트릭 값](../code-quality/code-metrics-values.md)합니다.

상속 깊이, 클래스 결합, 유지 관리 인덱스와 복잡성 규칙 적용 코드 분석 체크 인 정책을 통해 유지 관리 가능한 코드를 사용할 수 있습니다. 이러한 규칙의 모든 네는 코드 분석 정책 편집기에서 "유지 관리 규칙" 범주 아래 있습니다.

Team foundation 버전 제어의 관리자는 체크 인 정책 요구 사항에 코드 분석 유지 관리 규칙을 추가할 수 있습니다. 이러한 체크 인 정책에 따른 개발자는 코드 분석 체크 인 시작 하기 전에 이러한 규칙 변경 내용에 따라 실행할 수 있습니다.

## <a name="to-open-the-code-analysis-policy-editor"></a>코드 분석 정책 편집기를 열려면

1. **팀 탐색기**팀 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **팀 프로젝트 설정**, 클릭 하 고 **소스 제어**합니다.

     **소스 제어** 대화 상자가 나타납니다.

2. 에 **체크 인 정책** 탭을 클릭 **추가**합니다.

     **추가 체크 인 정책** 대화 상자가 나타납니다.

3. 에 **체크 인 정책** 목록, 선택는 **코드 분석** 확인란을 선택한 다음 클릭 **확인**합니다.

     **코드 분석 정책 편집기** 대화 상자가 나타납니다.

## <a name="to-enable-code-analysis-maintainability-rules"></a>코드 분석 유지 관리 규칙을 사용 하도록 설정 하려면

1. 에 **코드 분석 정책 편집기** 대화 상자의 **규칙 설정**를 확장 하 고는 **유지 관리 규칙** 노드.

2. 다음 규칙에 대 한 확인란을 선택 합니다.

    -   상속 깊이: **CA1501 AvoidExcessiveInheritance** -임계값: 5 개 이상의 사이에서 경고 발생

    -   복잡성: **CA1502 AvoidExcessiveComplexity** -임계값: 25 개 이상의에서 경고 발생

    -   유지 관리 인덱스: **CA1505 AvoidUnmaintainableCode** -임계값: 20, 미만 경고

    -   클래스 결합: **CA1506 AvoidExcessiveClassCoupling** -임계값: 클래스에 대 한 80 개 이상의 및 메서드에 대 한 30 개 이상의에서 경고 발생

    빌드에 성공 하지 않으려면 규칙 위반을 하려는 경우 또한 선택 된 **경고를 오류로** 규칙 설명 옆에 있는 확인란 합니다.

3. **확인**을 클릭합니다. 새 체크 인 정책은 이제 이후의 체크 인에 적용 됩니다.

## <a name="see-also"></a>참고 항목

- [코드 메트릭 값](../code-quality/code-metrics-values.md)
- [코드 분석 체크 인 정책 만들기 및 사용](../code-quality/creating-and-using-code-analysis-check-in-policies.md)