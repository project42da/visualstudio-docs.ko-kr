---
title: "DslTextTransform 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어에서 명령"
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: 30
caps.handback.revision: 30
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# DslTextTransform 명령
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

DslTextTransform.cmd는 TextTransform.exe를 호출 하 고 일반 옵션으로 실행 하는 스크립트입니다. DslTextTransformation.cmd를 사용 하 여의 야간 빌드를 자동화 하 여 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 프로젝트입니다. 자세한 내용은 참조 [TextTransform 유틸리티를 사용 하 여 파일 생성](../modeling/generating-files-with-the-texttransform-utility.md)합니다.  
  
 DslTextTransform.cmd은 다음 디렉터리에 있습니다.  
  
 **\< visual Studio SDK 설치 경로>\VisualStudioIntegration\Tools\Bin**  
  
 DslTextTransform.cmd에 대 한 입력으로 다음 인수를 지정할 수 있습니다.  
  
-   도메인 모델 프로젝트의 출력 디렉터리입니다.  
  
-   디자이너 정의 프로젝트의 출력 디렉터리입니다.  
  
-   텍스트 템플릿 파일의 위치입니다.  
  
 DslTextTransform.cmd 기본 지시문 프로세서 및 어셈블리를 사용 하 여 지정 된 텍스트 템플릿 파일을 처리 합니다. 사용자 지정 지시문 프로세서를 만드는 경우 TextTransform.exe를 호출 하는 배치 파일을 만들 수 있습니다. 이 배치 파일에서 어셈블리 및 연관 된 사용자 지정 지시문 프로세서를 지정할 수 있습니다.