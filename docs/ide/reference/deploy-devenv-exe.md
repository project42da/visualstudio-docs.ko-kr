---
title: -Deploy(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4561c8955f0ce4b1b5b50be8e31b5ff2ef5751d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
빌드 또는 다시 빌드 후 솔루션을 배포합니다. 관리 코드 프로젝트에만 적용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## <a name="arguments"></a>인수  
 `SolnConfigName`  
 필수 요소. `SolutionName`으로 명명된 솔루션을 빌드하는 데 사용할 솔루션 구성의 이름입니다.  
  
 `SolutionName`  
 필수 요소. 솔루션 파일의 전체 경로 및 이름입니다.  
  
 /project `ProjName`  
 선택 사항입니다. 솔루션 내에 있는 프로젝트 파일의 경로와 이름입니다. `SolutionName` 폴더에서 프로젝트 파일, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름까지의 상대 경로를 입력할 수 있습니다.  
  
 /projectconfig `ProjConfigName`  
 선택 사항입니다. `/project` 빌드 시 사용할 프로젝트 빌드 구성 이름입니다.  
  
## <a name="remarks"></a>설명  
 지정된 프로젝트는 배포 프로젝트여야 합니다. 지정된 프로젝트가 배포 프로젝트가 아닌 경우, 빌드된 프로젝트가 배포되도록 전달되면 오류로 인해 실패합니다.  
  
 공백을 포함하는 문자열은 큰따옴표로 묶습니다.  
  
 오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `MySolution`의 `Release` 솔루션 구성 내에 있는 `Release` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 배포합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [/Project(devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/Build(devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Clean(devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Rebuild(devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)