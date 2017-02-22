---
title: "/Build (devenv.exe) | Microsoft Docs"
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
  - "/build Devenv 스위치"
  - "build Devenv 스위치"
  - "빌드[Team System], 명령줄"
  - "Devenv, /build 스위치"
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Build (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 솔루션 구성 파일을 사용하여 솔루션을 빌드합니다.  
  
## 구문  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## 인수  
 `SolutionName`  
 필수 요소.  솔루션 파일의 전체 경로와 이름입니다.  
  
 `SolnConfigName`  
 필수 요소.  `SolutionName`에 명명된 솔루션을 빌드하는 데 사용할 솔루션 구성 이름입니다.  
  
 \/project `ProjName`  
 선택적 요소.  솔루션에 있는 프로젝트 파일의 경로 및 이름입니다.  `SolutionName` 폴더의 프로젝트 파일에 대한 상대 경로, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다.  
  
 \/projectconfig `ProjConfigName`  
 선택적 요소.  명명된 `/project`를 빌드할 때 사용할 프로젝트 빌드 구성 이름입니다.  
  
## 설명  
 이 스위치는 IDE\(통합 개발 환경\)의 **솔루션 빌드** 메뉴 명령과 같은 기능을 수행합니다.  
  
 공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
 오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시됩니다.  
  
 이 명령은 마지막 빌드 이후 변경된 프로젝트만 빌드합니다.  솔루션의 모든 프로젝트를 빌드하려면 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)를 사용합니다.  
  
## 예제  
 다음 예제에서는 `MySolution`의 `Debug` 솔루션 구성에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 빌드합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## 참고 항목  
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Clean](../../ide/reference/clean-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)