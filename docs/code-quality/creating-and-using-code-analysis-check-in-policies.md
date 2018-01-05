---
title: "코드 분석 체크 인 정책 만들기 및 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, check-in policies
ms.assetid: 3fa5a849-e05f-4e31-8ba3-b014c889d94d
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b7187ef8d3342ad050c66debf939e9c6a6213957
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-using-code-analysis-check-in-policies"></a>코드 분석 체크 인 정책 만들기 및 사용
버전 제어 TFVC (Team Foundation)를 사용 하면.NET Framework 및 팀 프로젝트에서 네이티브 (C/c + +) 코드 프로젝트에 대 한 코드 분석 체크 인 정책을 만들 수 있습니다. 코드 분석 체크 인 정책 제어 하 고 코드 베이스에 체크 인 되는 코드의 품질 향상에 사용할 수 있습니다.  
  
 로컬 빌드는 최신 버전 및 가장 최근의 소스 파일에서 코드 분석 실행 된이 정책을 통과 합니다. 여기에 최소한 코드 프로젝트에 설정 된 경우 코드 분석 규칙 팀 프로젝트 체크 인 정책에 정의 된 것과 같은 규칙을 포함 해야 합니다. 팀 프로젝트 설정에서 오류로 지정 된 규칙 코드 프로젝트에서 오류로 지정 해야  
  
> [!IMPORTANT]
>  웹 사이트 프로젝트에 코드 분석 체크 인 정책은 적용할 수 없습니다. 웹 응용 프로그램 프로젝트에 적용할 수 있습니다.  
  
 팀 프로젝트 설정을 사용 하 여 코드 분석 체크 인 정책을 만들어 [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]합니다. 체크 인 정책을 지정 되 고, 팀 프로젝트에 대 한 적용 하지만 코드 분석 실행 구성 되 고 로컬 개발 컴퓨터에서 개별 코드 프로젝트에 대해 실행 됩니다. 이 섹션에는 팀 프로젝트에 대 한 코드 분석 체크 인 정책을 지정 하는 방법 및 관리 코드에 대 한 사용자 지정 코드 분석 정책을 구현 하는 방법을 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 표준 코드 분석 체크 인 정책 만들기 또는 업데이트](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)  
 설정 하 고 수정할 팀 프로젝트에 대 한 코드 분석 정책을 사용 하는 단계에 설명 합니다.  
  
 [관리 코드에 대 한 사용자 지정 체크 인 정책 구현](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)  
 팀 프로젝트의 체크 인 정책에 대해 설정 하는 사용자 지정 규칙을 만드는 및 팀 프로젝트의 코드 프로젝트에서 체크 인 정책을 사용 하 여 동기화를 사용 하는 단계에 설명 합니다.  
  
 [코드 분석 체크 인 정책에 대한 버전 호환성](../code-quality/version-compatibility-for-code-analysis-check-in-policies.md)  
 버전 간에 코드 분석 체크 인 호환성 문제에 설명 [!INCLUDE[vstsLong](../code-quality/includes/vstslong_md.md)]합니다.  
  
 [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
 단어 및 토큰 코드 분석에 대 한 명명 규칙에서 참조 되는 사전에 추가 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)