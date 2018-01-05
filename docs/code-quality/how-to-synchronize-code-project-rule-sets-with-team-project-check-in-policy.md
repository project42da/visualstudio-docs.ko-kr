---
title: "방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 899f9026b2e7c86ad1bd9f722dc7e1904cab2b9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화
최소한 규칙 체크 인 정책에 대 한 집합에 지정 된 규칙을 포함 하는 규칙 집합을 지정 하 여 동기화 할 팀 프로젝트에 대 한 체크 인 정책에 코드 프로젝트에 대 한 코드 분석 설정이 있습니다. 수석 개발자는 사용자 이름 및 규칙 체크 인 정책에 대 한 집합의 위치에 알릴 수 있습니다. 코드 분석 프로젝트에 대 한 올바른 규칙 집합이 사용 하도록 다음 옵션 중 하나를 사용할 수 있습니다.  
  
-   체크 인 정책 Microsoft 기본 제공 규칙 집합 중 하나를 사용 하 고 코드 프로젝트에 대 한 속성 대화 상자를 엽니다, 그리고 코드 분석 페이지를 표시 및 코드 프로젝트 설정의 코드 분석 페이지에서 설정 하는 규칙을 선택 합니다. Microsoft 표준 규칙 집합은 Visual Studio와 함께 자동으로 설치 됩니다. 읽기 전용으로 설정 되 고 편집할 수 없습니다. 규칙 집합을 편집할 수 없는 경우 규칙의 정책 및 로컬 규칙 집합에 일치 하도록 보장 됩니다.  
  
-   체크 인 정책 사용자 지정 규칙 집합을 사용 하는 경우 로컬 복사본을 만들려는 버전 제어에서 규칙 집합 파일에 대 한 get 작업을 수행 합니다. 다음 코드 프로젝트에 대 한 코드 분석 설정에 해당 로컬 위치를 지정 합니다. 규칙은 일치 규칙 집합 체크 인 정책에 대 한 최신 상태 인지 보장 됩니다.  
  
     코드 프로젝트와 같은 팀 프로젝트 루트 관계에 있는 로컬 폴더에 버전 제어 위치를 매핑하는 경우 규칙의 위치가 상대 경로 사용 하 여 설정 됩니다. 상대 경로 사용 하면 코드 분석을 위한 코드 프로젝트 설정을 다른 컴퓨터로 이동할 수 있습니다.  
  
-   규칙 코드 프로젝트에 대 한 체크 인 정책에 대 한 집합의 복사본을 사용자 지정 합니다. 새 규칙 집합 포함할 다른 규칙 및 체크 인 정책에 있는 모든 규칙이 포함 되어 있는지 확인 합니다. 규칙 집합에서 규칙 집합 체크 인 정책에 대 한 모든 규칙이 포함 되어 있는지 확인 해야 합니다.  
  
### <a name="to-specify-a-microsoft-standard-rule-set"></a>Microsoft 표준 규칙을 지정  
  
1.  **솔루션 탐색기**코드 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
2.  클릭 **코드 분석**합니다.  
  
3.  에 **이 규칙 집합 실행** 목록에서 체크 인 정책에 규칙 집합을 클릭 합니다.  
  
### <a name="to-specify-a-custom-check-in-policy-rule-set"></a>사용자 지정 체크 인 정책 규칙 집합을 지정 하려면  
  
1.  필요한 경우 체크 인 정책을 지정 하는 규칙 집합 파일에 대 한 get 작업을 수행 합니다.  
  
2.  **솔루션 탐색기**코드 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
3.  클릭 **코드 분석**합니다.  
  
4.  에 **이 규칙 집합 실행** 목록에서 클릭  **\<찾아보기... >**합니다.  
  
5.  에 **열려** 대화 상자, 체크 인 정책에 규칙 집합 파일을 지정 합니다.  
  
### <a name="to-create-a-custom-rule-set-for-a-code-project"></a>코드 프로젝트에 대 한 집합을 사용자 지정 규칙을 만들려면  
  
1.  프로젝트 설정 대화 상자의 코드 분석 페이지에서 팀 프로젝트의 체크 인 정책을 선택 하려면이 항목의 앞부분에 나오는 절차 중 하나를 수행 합니다.  
  
2.  클릭 **열려**합니다.  
  
3.  추가 하거나 규칙 집합 편집기를 사용 하 여 규칙을 제거 합니다.  
  
     자세한 내용은 참조 [사용자 지정 규칙 집합 만들기](../code-quality/creating-custom-code-analysis-rule-sets.md)합니다.  
  
4.  로컬 컴퓨터에 있는.ruleset 파일 또는 UNC 경로를 설정 하 여 수정 된 규칙을 저장 합니다.  
  
5.  코드 프로젝트에 대 한 속성 대화 상자를 열고 표시 된 **코드 분석** 페이지.  
  
6.  에 **이 규칙 집합 실행** 목록에서 클릭  **\<찾아보기... >**합니다.  
  
7.  에 **열려** 대화 상자에서 규칙 집합 파일을 지정 합니다.