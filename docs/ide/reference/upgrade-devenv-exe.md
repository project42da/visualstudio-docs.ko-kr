---
title: "/Upgrade (devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/upgrade 스위치"
  - "Devenv, /upgrade 스위치"
  - "upgrade 스위치"
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
caps.latest.revision: 18
caps.handback.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Upgrade (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션 파일과 솔루션의 모든 프로젝트 파일 또는 지정한 프로젝트 파일을 이러한 파일의 현재 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 형식으로 업데이트합니다.  
  
## 구문  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## 인수  
 `SolutionFile`  
 전체 솔루션과 해당 프로젝트를 업그레이드하는 경우 필수적 요소.  솔루션 파일의 경로 및 이름입니다.  솔루션 파일의 이름만 입력하거나 솔루션 파일의 전체 경로와 이름을 입력할 수 있습니다.  명명된 폴더나 파일이 아직 없으면 만들어집니다.  
  
 `ProjectFile`  
 단일 프로젝트를 업그레이드하는 경우 필수적 요소.  솔루션에 있는 프로젝트 파일의 경로 및 이름입니다.  프로젝트 파일의 이름만 입력하거나 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다.  명명된 폴더나 파일이 아직 없으면 만들어집니다.  
  
## 설명  
 백업이 자동으로 만들어지고 현재 디렉터리에 만들어지는 Backup이라는 디렉터리에 복사됩니다.  
  
 소스 제어에서 사용 중인 솔루션이나 프로젝트는 체크 아웃한 후 업그레이드할 수 있습니다.  
  
 `/upgrade` 스위치를 사용하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 시작되지 않습니다.  업그레이드 결과는 솔루션이나 프로젝트 개발 언어의 업그레이드 보고서에 표시됩니다.  오류나 사용법 정보는 반환되지 않습니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)를 참조하십시오.  
  
## 예제  
 이 예제에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 솔루션의 기본 폴더에 있는 "MyProject.sln"이라는 솔루션 파일을 업그레이드합니다.  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## 참고 항목  
 [방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)