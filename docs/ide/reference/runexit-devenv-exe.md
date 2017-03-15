---
title: "/Runexit (devenv.exe) | Microsoft Docs"
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
  - "/runexit Devenv 스위치"
  - "Devenv, /runexit 스위치"
  - "runexit Devenv 스위치"
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Runexit (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 프로젝트나 솔루션을 컴파일하고 실행한 다음 IDE\(통합 개발 환경\)를 닫습니다.  
  
## 구문  
  
```  
devenv /runexit {SolutionName|ProjectName}  
```  
  
## 인수  
 `SolutionName`  
 필수 요소.  솔루션 파일의 전체 경로와 이름입니다.  
  
 `ProjectName`  
 필수 요소.  프로젝트 파일의 전체 경로와 이름입니다.  
  
## 설명  
 지정된 프로젝트 또는 솔루션을 활성 솔루션 구성에 대해 지정된 설정에 따라 컴파일하고 실행합니다.  이 스위치는 프로젝트나 솔루션을 실행하는 동안 IDE를 최소화하며, 프로젝트나 솔루션의 실행을 마친 후 IDE를 닫습니다.  
  
-   공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시됩니다.  
  
## 예제  
 다음 예제에서는 활성 배포 구성을 사용하여 최소화된 IDE에서 `MySolution` 솔루션을 실행한 다음 IDE를 닫습니다.  
  
```  
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Run](../../ide/reference/run-devenv-exe.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)