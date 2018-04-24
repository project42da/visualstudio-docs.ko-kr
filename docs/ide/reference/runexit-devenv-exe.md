---
title: -Runexit(devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- runexit Devenv switch
- Devenv, /runexit switch
- /runexit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e52d305fd58239b13fe3cc0aaab0fc6a19522c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="runexit-devenvexe"></a>/Runexit (devenv.exe)
지정된 프로젝트 또는 솔루션을 컴파일 및 실행한 다음 IDE(통합 개발 환경)을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /runexit {SolutionName|ProjectName}  
```  
  
## <a name="arguments"></a>인수  
 `SolutionName`  
 필수. 솔루션 파일의 전체 경로 및 이름입니다.  
  
 `ProjectName`  
 필수. 프로젝트 파일의 전체 경로 및 이름입니다.  
  
## <a name="remarks"></a>설명  
 활성 솔루션 구성에 대해 지정된 설정에 따라 지정된 프로젝트 또는 솔루션을 컴파일하고 실행합니다. 이 스위치는 프로젝트 또는 솔루션을 실행하는 동안 IDE를 최소화하고 프로젝트 또는 솔루션 실행을 완료한 후에 IDE를 닫습니다.  
  
-   공백을 포함하는 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 활성 배포 구성을 사용하여 최소화된 IDE에서 `MySolution` 솔루션을 실행한 다음 IDE를 닫습니다.  
  
```  
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [/Run(devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/Build(devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Rebuild(devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)