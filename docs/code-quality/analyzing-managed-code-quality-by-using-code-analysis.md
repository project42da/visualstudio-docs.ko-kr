---
title: "코드 분석을 사용하여 관리 코드 품질 분석 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 관리 코드"
  - "관리 코드 분석"
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 24
---
# 코드 분석을 사용하여 관리 코드 품질 분석
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 에서 코드 분석을 사용하여 비보안 데이터 액세스, 사용법 위반 및 디자인 문제와 같은 코드의 잠재적 문제를 찾을 수 있습니다.  코드 분석은 .NET Framework, 네이티브\(C 및 C\+\+\) 및 데이터베이스 응용 프로그램에 대해 사용할 수 있습니다.  관리 코드에 대한 코드 분석에서는 특정 코딩 문제를 대상으로 하는 *규칙 집합*으로 규칙을 구성합니다.  
  
## 일반 작업  
  
|일반 작업|지원 내용|  
|-----------|-----------|  
|**실습:** 간단한 .NET Framework 응용 프로그램의 결함을 수정해 봄으로써 코드 분석의 기본 사항을 익힙니다.|-   [연습: 관리 코드의 코드 오류 분석](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|  
|**프로젝트에 대한 코드 분석 구성:** 관리 코드에 대한 규칙은 보안 및 디자인과 같은 특정 영역을 대상으로 하는 규칙 집합으로 구성됩니다.  Microsoft 표준 규칙 집합 중 하나를 사용하거나 규칙 집합을 직접 만들 수 있습니다.|-   [관리 코드에 대한 코드 분석 개요](../code-quality/code-analysis-for-managed-code-overview.md)<br />-   [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)<br />-   [SuppressMessage 특성을 사용하여 경고 표시 안 함](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|  
|**코드 분석 실행:** 프로젝트 구성이 빌드될 때마다 코드 분석이 자동으로 실행되도록 지정하거나, 프로젝트에 대해 코드 분석을 수동으로 실행할 수 있습니다.|-   [방법: 자동 코드 분석 사용 설정 및 해제](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Code%20Analysis%20for%20Managed%20Code.md)<br />-   [방법: 수동으로 코드 분석 실행](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|  
|**코드 분석 결과 분석:** 코드 분석 경고 및 오류는 코드 분석창에 표시됩니다.  경고에 대한 추가 정보를 표시하고 규칙을 발생시킨 소스 코드 줄에 강조표시를 하기위해 경고 또는 오류를 선택할 수 있습니다.  문제에 대한 정보와 이 문제를 해결 하는 방법의 예제를 포함 하는 MSDN Library에서 자세한 정보를 표시 하도록 경고 id를 선택할 수 있습니다.|-   [방법: 관리 코드 오류 보기](../code-quality/how-to-view-managed-code-defects.md)<br />-   [관리 코드 경고에 대한 코드 분석](../code-quality/code-analysis-for-managed-code-warnings.md)<br />-   [CheckId별 경고](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [무명 메서드 및 코드 분석](../code-quality/anonymous-methods-and-code-analysis.md)|  
|**개발 주기와 코드 분석 통합:** 개발 팀에서는 [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]의 체크 인 정책을 사용하여 모든 코드 체크 인이 일반적인 코드 분석 표준 집합을 충족하는지 확인할 수 있습니다.  오류 목록 창에서는 코드 분석 규칙 위반에 대한 작업 항목을 손쉽게 만들 수 있습니다.|-   [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [방법: 관리 코드 오류에 대한 작업 항목 만들기](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|