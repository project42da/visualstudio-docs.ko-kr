---
title: "규칙 집합을 사용하여 코드 분석 규칙 그룹화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.rulesets.learnmore"
helpviewer_keywords: 
  - "코드 분석, 규칙 집합"
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 36
---
# 규칙 집합을 사용하여 코드 분석 규칙 그룹화
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]에서 코드 분석을 구성할 때 Microsoft 기본 제공 *규칙 집합*목록에서 규칙 집합을 선택할 수 있습니다.  규칙 집합은 대상 영역의 문제 및 특정 조건을 식별하는 코드 분석 규칙을 논리적으로 그룹화한 것입니다.  예를 들어 코드에서 공개적으로 사용 가능한 API를 검사하도록 디자인된 규칙 집합을 적용하거나, 최소 권장 규칙만 포함된 규칙 집합을 적용할 수 있습니다. 모든 규칙이 포함된 규칙 집합을 적용할 수도 있습니다.  모든 규칙이 포함된 규칙 집합을 적용할 수도 있습니다.  
  
 규칙을 추가 또는 삭제하거나 **오류 목록** 창에 경고나 오류로 표시할 규칙을 변경하여 규칙 집합을 사용자 지정할 수 있습니다.  사용자 지정된 규칙 집합은 특정 개발 환경의 요구 사항을 충족할 수 있습니다.  규칙 집합을 사용자 지정할 때 규칙 집합 페이지에서는 사용자 지정 과정을 돕는 검색 및 필터링 도구가 제공됩니다.  
  
## 일반 작업  
  
|Task|관련 내용|  
|----------|-----------|  
|**실습:** 코드 분석 도구를 사용하여 간단한 .NET Framework 응용 프로그램의 문제를 찾고 해결하기 위한 사용자 지정 규칙 집합을 지정합니다.|-   [연습: 사용자 지정 규칙 집합 구성 및 사용](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**프로젝트에 대한 코드 분석 구성:** 프로젝트, 웹 사이트 또는 솔루션에 적용할 기존 규칙 집합을 선택합니다.|-   [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [규칙 집합을 사용하여 실행할 C\+\+ 규칙 지정](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [방법: 솔루션의 여러 프로젝트에 대한 관리 규칙 집합 지정](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**규칙 집합 사용자 지정:** 프로젝트에 적용할 규칙을 지정합니다.|-   [사용자 지정 규칙 집합 만들기](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**기본 제공 규칙 집합 이해:** 기본 제공 규칙 집합을 구성하는 코드 분석 규칙을 봅니다.|-   [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)|  
|**Team Foundation Server와 코드 분석 통합:**개발 팀에서는[!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 체크 인 정책을 사용하여 모든 코드 체크 인이 일반적인 코드 분석 표준 집합을 충족하는지 확인할 수 있습니다.|-   [방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|