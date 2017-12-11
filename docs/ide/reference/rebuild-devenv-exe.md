---
title: -Rebuild(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fcabe7b1ce4130eb52369ff9f16900b1979b8582
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
지정된 솔루션 구성을 정리하고 빌드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>인수  
 `SolnConfigName`  
 필수 요소. `SolutionName`으로 명명된 솔루션을 다시 빌드하는 데 사용할 솔루션 구성의 이름입니다.  
  
 `SolutionName`  
 필수 요소. 솔루션 파일의 전체 경로 및 이름입니다.  
  
 /project `ProjName`  
 선택 사항입니다. 솔루션 내에 있는 프로젝트 파일의 경로와 이름입니다. `SolutionName` 폴더에서 프로젝트 파일, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름까지의 상대 경로를 입력할 수 있습니다.  
  
 /projectconfig `ProjConfigName`  
 선택 사항입니다. `/project` 다시 빌드 시 사용할 프로젝트 빌드 구성 이름입니다.  
  
## <a name="remarks"></a>설명  
  
-   이 스위치는 IDE(통합 개발 환경)내에서 **솔루션 다시 빌드** 메뉴 명령과 동일한 기능을 수행합니다.  
  
-   공백을 포함하는 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 정리 및 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `MySolution`의 `Debug` 솔루션 구성 내에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpWinApp` 프로젝트를 정리하고 다시 빌드합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [/Build(devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Clean(devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)