---
title: "/Run (devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/r Devenv 스위치"
  - "/run Devenv"
  - "응용 프로그램[Visual Studio], 실행"
  - "Devenv, /run 스위치"
  - "r Devenv 스위치(/r)"
  - "Devenv 스위치 실행"
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Run (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 프로젝트나 솔루션을 컴파일하고 실행합니다.  
  
## 구문  
  
```  
devenv {/run|/r} {SolutionName|ProjectName}  
```  
  
## 인수  
 `SolutionName`  
 필수 요소.  솔루션 파일의 전체 경로와 이름입니다.  
  
 `ProjectName`  
 필수 요소.  프로젝트 파일의 전체 경로와 이름입니다.  
  
## 설명  
 지정된 프로젝트 또는 솔루션을 활성 솔루션 구성에 대해 지정된 설정에 따라 컴파일하고 실행합니다.  이 스위치는 IDE\(통합 개발 환경\)를 시작하며, 프로젝트나 솔루션의 실행을 마친 후 IDE를 활성 상태로 둡니다.  
  
-   공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시됩니다.  
  
## 예제  
 다음 예제에서는 활성 배포 구성을 사용하여 `MySolution` 솔루션을 실행합니다.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Runexit](../../ide/reference/runexit-devenv-exe.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)