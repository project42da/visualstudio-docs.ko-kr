---
title: "/Project (devenv.exe) | Microsoft Docs"
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
  - "/project Devenv 스위치"
  - "배포 프로젝트, 지정"
  - "Devenv, /project 스위치"
  - "project Devenv 스위치(/project)"
  - "프로젝트[Visual Studio], 빌드"
  - "프로젝트[Visual Studio], 정리"
  - "프로젝트[Visual Studio], 다시 빌드"
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Project (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 솔루션 구성에서 빌드하거나, 정리하거나, 다시 빌드하거나, 배포할 단일 프로젝트를 식별합니다.  
  
## 구문  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName   
[/project ProjName] [/projectconfig ProjConfigName]   
```  
  
## 인수  
 \/build  
 `/project`  `ProjName`으로 지정된 프로젝트를 빌드합니다.  
  
 \/clean  
 빌드 중에 만들어진 매개자 파일 및 출력 디렉터리를 모두 정리합니다.  
  
 \/rebuild  
 `/project`  `ProjName`으로 지정된 프로젝트를 정리한 다음 빌드합니다.  
  
 \/deploy  
 빌드하거나 다시 빌드한 후 프로젝트가 배포되도록 지정합니다.  
  
 `SolnConfigName`  
 필수 요소.  `SolutionName`에 명명된 솔루션에 적용할 솔루션 구성 이름입니다.  
  
 `SolutionName`  
 필수 요소.  솔루션 파일의 전체 경로와 이름입니다.  
  
 \/project `ProjName`  
 선택적 요소.  솔루션에 있는 프로젝트 파일의 경로 및 이름입니다.  `SolutionName` 폴더의 프로젝트 파일에 대한 상대 경로, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다.  
  
 \/projectconfig `ProjConfigName`  
 선택적 요소.  명명된 `/project`에 적용할 프로젝트 빌드 구성의 이름입니다.  
  
## 설명  
  
-   `devenv /build`, \/`clean`, `/rebuild` 또는 `/deploy` 명령의 일부로 사용해야 합니다.  
  
-   공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시됩니다.  
  
## 예제  
 다음 예제에서는 `MySolution`의 `Debug` 솔루션 구성에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 빌드합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/ProjectConfig](../../ide/reference/projectconfig-devenv-exe.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Clean](../../ide/reference/clean-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Deploy](../../ide/reference/deploy-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)