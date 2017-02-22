---
title: "/Clean (devenv.exe) | Microsoft Docs"
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
  - "/clean Devenv 스위치"
  - "빌드[Team System], 파일 정리"
  - "clean Devenv 스위치"
  - "Devenv, /clean 스위치"
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Clean (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

매개자 파일 및 출력 디렉터리를 모두 정리합니다.  
  
## 구문  
  
```  
devenv FileName /Clean [ /project projectnameorfile [/projectconfig name ] ]  
```  
  
## 인수  
 `FileName`  
 필수 요소.  솔루션 파일 또는 프로젝트 파일의 전체 경로와 이름입니다.  
  
 \/project `ProjName`  
 선택적 요소.  솔루션에 있는 프로젝트 파일의 경로 및 이름입니다.  `SolutionName` 폴더의 프로젝트 파일에 대한 상대 경로, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다.  
  
 \/projectconfig `ProjConfigName`  
 선택적 요소.  명명된 `/project`를 정리할 때 사용할 프로젝트 빌드 구성 이름입니다.  
  
## 설명  
 이 스위치는 IDE\(통합 개발 환경\)의 **솔루션 정리** 메뉴 명령과 같은 기능을 수행합니다.  
  
 공백이 포함된 문자열은 큰따옴표로 묶습니다.  
  
 오류를 포함한 정리 및 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정한 로그 파일에 표시됩니다.  
  
## 예제  
 첫 번째 예제는 솔루션 파일에 지정된 기본 구성을 사용하여 `MySolution` 솔루션을 지웁니다.  
  
 두 번째 예제에서는 `MySolution`의 `Debug` 솔루션 구성에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 정리합니다.  
  
```  
Devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean  
  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"   
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Out](../../ide/reference/out-devenv-exe.md)