---
title: 디버거에서 Dll 및 실행 파일을 볼 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46dc913b95396e16f208611bcfc926378609bef6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>Dll 및 Visual Studio 디버거에서 모듈 창을 사용 하 여 실행 파일을 보려면
 
**모듈** Dll 및 실행 파일 (EXE) 프로그램에 사용 되 고 각각에 대 한 관련 정보가 표시 창에 표시 합니다. 

> [!NOTE]
>  SQL 또는 스크립트 디버깅에는 이 기능을 사용할 수 없습니다. 
  
### <a name="to-display-the-modules-window"></a>모듈 창을 표시 하려면  
  
-   디버깅 하는 동안 선택 **디버그 > Windows** 클릭 하 고 **모듈**합니다.  
  
     기본적으로는 **모듈** 창에서는 모듈이 로드 순서 대로 정렬 합니다. 그러나 열을 기준으로 정렬할 수도 있습니다.  
  
### <a name="to-sort-by-any-column"></a>열별로 정렬하려면  
  
-   정렬 기준이 될 열 맨 위에 있는 단추를 클릭합니다.  
  
     기호를 로드 하거나 기호 경로 지정할 수 있습니다는 **모듈** 바로 가기 메뉴를 사용 하 여 창.  
  
## <a name="loading-symbols"></a>기호 로드  
 에 **모듈** 창에서 디버깅 기호가 로드 된 모듈을 확인할 수 있습니다. 이 정보에 표시 된 **기호 상태** 열입니다. 상태가 **건너뜀 loadingCannot 찾거나 PDB 파일을 열**, 또는 **포함/제외 설정으로 로드가 비활성화 되었습니다**, Microsoft 공용 기호에서 기호를 다운로드 하도록 디버거에 지시할 수 있습니다 서버 또는 컴퓨터의 기호 경로에서 기호를 로드 합니다. 자세한 내용은 참조 [지정 기호 (.pdb) 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>기호를 수동으로 로드하려면  
  
1.  에 **모듈** 창에서 기호가 로드 되지 않은 모듈 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **에서 기호 로드** 클릭 하 고 **Microsoft 기호 서버** 또는 **기호 경로**합니다.  
  
#### <a name="to-change-symbol-load-settings"></a>기호 로드 설정을 변경하려면  
  
1.  에 **모듈** 창에서 모든 모듈을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  클릭 **설정을 기호**합니다.  
  
     에 설명 된 대로 이제 기호 로드 설정의 변경할 수 있습니다 [기호 위치를 지정 하 고 로드 동작](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior)합니다. 디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>특정 모듈에 대한 기호 로드 동작을 변경하려면  
  
1.  에 **모듈** 창 모듈을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **기호 로드 자동 설정** 클릭 하 고 **항상 수동으로 로드** 또는 **기본**합니다. 디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [중단과 실행 중지](http://msdn.microsoft.com/en-us/30fc4643-f337-4651-b1ff-f2de2c098d40)   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)