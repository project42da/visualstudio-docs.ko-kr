---
title: "DslTextTransform 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 47b64bf5049baf981cbf85ec5bfeba4f5f796636
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 명령
DslTextTransform.cmd는 TextTransform.exe를 호출 하 고 일반 옵션으로 실행 하는 스크립트입니다. DslTextTransformation.cmd를 사용 하 여의 야간 빌드를 자동화 하 여 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 프로젝트. 자세한 내용은 참조 [TextTransform 유틸리티를 사용 하 여 파일 생성](../modeling/generating-files-with-the-texttransform-utility.md)합니다.  
  
 DslTextTransform.cmd은 다음 디렉터리에 있습니다.  
  
 **\<Visual Studio SDK 설치 경로 > \VisualStudioIntegration\Tools\Bin**  
  
 DslTextTransform.cmd 입력으로는 다음 인수를 지정할 수 있습니다.  
  
-   도메인 모델 프로젝트의 출력 디렉터리입니다.  
  
-   디자이너에서 정의 프로젝트의 출력 디렉터리입니다.  
  
-   텍스트 템플릿 파일의 위치입니다.  
  
 DslTextTransform.cmd 기본 지시문 프로세서 및 어셈블리를 사용 하 여 지정 된 텍스트 템플릿 파일을 처리 합니다. 사용자 지정 지시문 프로세서를 만들면 TextTransform.exe를 호출 하는 배치 파일을 만들 수 있습니다. 이 배치 파일에서 어셈블리 및 연관 된 사용자 지정 지시문 프로세서를 지정할 수 있습니다.