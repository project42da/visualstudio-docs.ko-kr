---
title: -Build(devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cc01dac34723f2a587e76461d41a60361a72091
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)
지정된 솔루션 구성 파일을 사용하여 솔루션을 빌드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## <a name="arguments"></a>인수  
 `SolutionName`  
 필수. 솔루션 파일의 전체 경로 및 이름입니다.  
  
 `SolnConfigName`  
 필수. `SolutionName`으로 명명된 솔루션을 빌드하는 데 사용할 솔루션 구성의 이름입니다.  
  
 /project `ProjName`  
 선택 사항입니다. 솔루션 내에 있는 프로젝트 파일의 경로와 이름입니다. `SolutionName` 폴더에서 프로젝트 파일, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름까지의 상대 경로를 입력할 수 있습니다.  
  
 /projectconfig `ProjConfigName`  
 선택 사항입니다. `/project` 빌드 시 사용할 프로젝트 빌드 구성 이름입니다.  
  
## <a name="remarks"></a>설명  
 이 스위치는 IDE(통합 개발 환경)내에서 **솔루션 빌드** 메뉴 명령과 동일한 기능을 수행합니다.  
  
 공백을 포함하는 문자열은 큰따옴표로 묶습니다.  
  
 오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.  
  
 이 명령은 마지막 빌드 이후 변경된 프로젝트만을 빌드합니다. 솔루션에서 모든 프로젝트를 빌드하려면 [/Rebuild(devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)를 사용합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 `MySolution`의 `Debug` 솔루션 구성 내에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 빌드합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [/Rebuild(devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Clean(devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)