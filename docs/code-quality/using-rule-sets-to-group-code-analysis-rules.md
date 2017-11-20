---
title: "코드 분석 규칙 그룹화를 설정 하는 규칙을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.rulesets.learnmore
helpviewer_keywords: code analysis, rule sets
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 44d64b7371f1b27afaa7796dc42d4b7864d20819
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="using-rule-sets-to-group-code-analysis-rules"></a>규칙 집합을 사용하여 코드 분석 규칙 그룹화
코드 분석을 구성할 때 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], Microsoft 기본 제공 목록에서 선택할 수 있습니다 *규칙 집합*합니다. 규칙 집합은 대상된 문제 및 특정 조건을 식별 하는 코드 분석 규칙의 논리적 그룹입니다. 예를 들어 공개적으로 사용할 수 있는 Api에 대 한 코드를 검색 하도록 디자인 된 규칙 집합을 적용할 수 하거나 최소 권장 규칙을 포함 하는 규칙 집합을 적용할 수 있습니다. 또한 모든 규칙을 포함 하는 규칙 집합을 적용할 수 있습니다.  
  
 규칙에 추가 또는 삭제 규칙 또는 규칙을 변경 하 여 집합을 사용자 지정할 수는 **오류 목록** 경고 또는 오류 창. 사용자 지정 된 규칙 집합에는 특정 개발 환경의 요구 사항을 충족할 수 있습니다. 규칙 집합을 사용자 지정 규칙 집합 페이지 검색 및 필터링 하는 프로세스의 도구를 제공 합니다.  
  
## <a name="common-tasks"></a>일반 작업  
  
|작업|관련 내용|  
|----------|---------------------|  
|**실습 가져오기:** 사용 하 여 사용자 지정 규칙을 지정 하려면 코드 분석 도구를 찾아서 간단한.NET Framework 응용 프로그램의 문제를 해결 설정 합니다.|-   [연습: 구성 및 사용자 지정 규칙 집합 사용](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**프로젝트에 대 한 코드 분석 구성:** 프로젝트, 웹 사이트 또는 솔루션에 대 한 기존 규칙 선택 합니다.|-   [방법: 관리 코드 프로젝트에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [규칙 집합을 사용 하 여 실행을 위해 c + + 규칙을 지정 하려면](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [방법: ASP.NET 웹 응용 프로그램에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [방법: 솔루션의 여러 프로젝트에 대 한 규칙 집합 지정](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**규칙 집합을 사용자 지정:** 프로젝트에 적용할 규칙을 지정 합니다.|-   [사용자 지정 규칙 집합 만들기](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**기본 제공 규칙 집합 이해:** 기본 제공 규칙 집합을 구성 하는 코드 분석 규칙을 확인 합니다.|-   [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)|  
|**코드 분석 Team Foundation Server와 통합:** [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 체크 인 정책을 개발 팀이 모든 코드 체크 인 코드 분석 표준의 공통 집합을 충족 하는지 확인 하는 데 사용 합니다.|-   [방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|