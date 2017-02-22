---
title: "/Deploy (devenv.exe) | Microsoft Docs"
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
  - "/deploy Devenv 스위치"
  - "deploy Devenv 스위치"
  - "응용 프로그램 배포[Visual Studio], 빌드 후"
  - "Devenv, /deploy 스위치"
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Deploy (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

빌드하거나 다시 빌드한 후 솔루션을 배포합니다.  관리 코드 프로젝트에만 적용됩니다.  
  
## 구문  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## 인수  
 `SolnConfigName`  
 필수 요소.  `SolutionName`에 명명된 솔루션을 빌드하는 데 사용할 솔루션 구성 이름입니다.  
  
 `SolutionName`  
 필수 요소.  솔루션 파일의 전체 경로와 이름입니다.  
  
 \/project `ProjName`  
 선택적 요소.  솔루션에 있는 프로젝트 파일의 경로 및 이름입니다.  `SolutionName` 폴더의 프로젝트 파일에 대한 상대 경로, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다.  
  
 \/projectconfig `ProjConfigName`  
 선택적 요소.  명명된 `/project`를 빌드할 때 사용할 프로젝트 빌드 구성 이름입니다.  
  
## 설명  
 지정된 프로젝트는 배포 프로젝트여야 합니다.  지정된 프로젝트가 배포 프로젝트가 아닌 경우 빌드된 프로젝트를 배포하기 위해 전달하면 오류가 발생하여 작업이 수행되지 않습니다.  
  
 공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
 오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시됩니다.  
  
## 예제  
 다음 예제에서는 `MySolution`의 `Release` 솔루션 구성에 있는 `Release` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 배포합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Project](../../ide/reference/project-devenv-exe.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Clean](../../ide/reference/clean-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)