---
title: "코드 분석 체크 인 정책 만들기 및 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/12/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 체크 인 정책"
ms.assetid: 3fa5a849-e05f-4e31-8ba3-b014c889d94d
caps.latest.revision: 39
caps.handback.revision: 39
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 코드 분석 체크 인 정책 만들기 및 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

TFVC\(Team Foundation Version Control\)를 사용하는 경우 팀 프로젝트에서 .NET Framework 및 네이티브\(C\/C\+\+\) 코드 프로젝트에 대한 코드 분석 체크 인 정책을 만들 수 있습니다.  코드 분석 체크 인 정책을 사용하면 코드베이스에 체크 인된 코드의 품질을 제어하고 향상시킬 수 있습니다.  
  
 로컬 빌드가 최신 상태이고 코드 분석이 가장 최근의 소스 파일에 대해 실행되었으면 이 정책을 통과하게 됩니다.  최소한 코드 프로젝트에서 사용하도록 설정된 코드 분석 규칙에는 팀 프로젝트 체크 인 정책에 정의된 것과 동일한 규칙이 포함되어 있어야 합니다.  또한 팀 프로젝트 설정에서 오류로 지정된 규칙은 코드 프로젝트에서도 오류로 지정되어야 합니다.  
  
> [!IMPORTANT]
>  코드 분석 체크 인 정책을 웹 사이트 프로젝트에 적용할 수 없습니다.  웹 응용 프로그램 프로젝트에 적용될 수 있습니다.  
  
 [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]의 팀 프로젝트 설정을 사용하여 코드 분석 체크 인 정책을 만들 수 있습니다.  체크 인 정책은 팀 프로젝트에 대해 지정 및 적용되지만 코드 분석 실행은 로컬 개발 컴퓨터의 개별 프로젝트에 대해 구성 및 실행됩니다.  이 단원에서는 팀 프로젝트에 대한 코드 분석 체크 인 정책을 지정하는 방법과 관리 코드에 대한 사용자 지정 코드 분석 정책을 구현하는 방법을 설명합니다.  
  
## 단원 내용  
 [방법: 표준 코드 분석 체크 인 정책 만들기 또는 업데이트](../Topic/How%20to:%20Create%20or%20Update%20Standard%20Code%20Analysis%20Check-in%20Policies.md)  
 팀 프로젝트의 코드 분석 정책을 설정 및 수정하는 데 필요한 단계를 설명합니다.  
  
 [관리 코드에 대한 사용자 지정 체크 인 정책 구현](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)  
 팀 프로젝트의 체크 인 정책에 사용할 사용자 지정 규칙 집합을 만들고, 팀 프로젝트의 코드 프로젝트를 체크 인 정책과 동기화하는 데 필요한 단계를 설명합니다.  
  
 [코드 분석 체크 인 정책에 대한 버전 호환성](../code-quality/version-compatibility-for-code-analysis-check-in-policies.md)  
 [!INCLUDE[vstsLong](../code-quality/includes/vstslong_md.md)] 버전 간의 코드 분석 체크 인 호환성 문제에 대해 설명합니다.  
  
 [방법: 코드 분석 사전 사용자 지정](../Topic/How%20to:%20Customize%20the%20Code%20Analysis%20Dictionary.md)  
 코드 분석 명명 규칙에서 참조하는 사전에 단어 및 토큰을 추가하는 방법을 설명합니다.  
  
## 관련 단원  
 [Set and Enforce Quality Gates](../Topic/Set%20and%20Enforce%20Quality%20Gates.md)  
  
 [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)