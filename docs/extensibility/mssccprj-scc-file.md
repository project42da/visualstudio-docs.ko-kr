---
title: MSSCCPRJ 합니다. SCC 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, MSSCCPRJ.SCC file
- MSSCCPRJ.SCC file
ms.assetid: 6f2e39d6-b79d-407e-976f-b62a3cedd378
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef076a93d27cc2c133404d6fe6463d32cb449956
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="mssccprjscc-file"></a>MSSCCPRJ 합니다. SCC 파일
Visual Studio 솔루션이 나 프로젝트를 IDE를 사용 하는 소스 제어에 배치 되 면 IDE 문자열의 형태로 플러그 인 소스 제어에서 두 가지 주요 정보를 받습니다. 이러한 문자열에 "AuxPath" 및 "ProjName"는 불투명 IDE에는 있지만 사용 플러그 인에서 버전 제어에서 솔루션이 나 프로젝트를 찾으려고 합니다. IDE 일반적으로 이러한 문자열 처음으로 호출 하 여 가져옵니다는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md), 이후 호출에 대 한 솔루션 또는 프로젝트 파일에 다음 저장 하 고는 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다. 솔루션 및 프로젝트 파일에 포함 된, "AuxPath" 및 "ProjName" 문자열은 자동으로 업데이트 되지 사용자 분기를 분기 지점 또는 버전 제어에 있는 솔루션 및 프로젝트 파일을 복사 하는 경우. 사용자가 솔루션 및 프로젝트 파일 버전 제어에서의 올바른 위치를 가리키는지 확인 하기 위해 문자열 수동으로 업데이트 해야 합니다. 문자열은 불투명으로 제공, 때문에 것 항상 않을 지우기 업데이트 방법을 합니다.  
  
 소스 제어 플러그 인은 MSSCCPRJ 라는 특수 파일에 "AuxPath" 및 "ProjName" 문자열을 저장 하 여이 문제를 방지할 수 있습니다. SCC 파일입니다. 가 소유 하 고 플러그 인에서 유지 관리 하는 로컬, 클라이언트 쪽 파일입니다. 이 파일은 소스 제어에서 접수 되지 되지만 소스 제어 파일에 있는 모든 디렉터리에 대 한 플러그 인에서 생성 됩니다. 어떤 파일은 Visual Studio 솔루션 및 프로젝트 파일을 확인 하려면 소스 제어 플러그 인 표준 또는 사용자가 제공한 목록에 대해 파일 확장명을 비교할 수 있습니다. 일단 IDE 플러그 인을 지원 하는지는 MSSCCPRJ 감지 합니다. SCC 파일 비게 "AuxPath"를 포함 하 고 솔루션 및 프로젝트 파일에 "ProjName" 문자열은 MSSCCPRJ에서 이러한 문자열을 읽습니다. SCC 파일 대신 합니다.  
  
 소스 제어 플러그 인을 지 원하는 MSSCCPRJ 합니다. SCC 파일은 다음 지침을 따라야 합니다.  
  
-   하나의 MSSCCPRJ 하나만 있을 수 있습니다. 디렉터리 당 SCC 파일입니다.  
  
-   MSSCCPRJ 합니다. SCC 파일 내 지정된 된 디렉터리에서 소스 제어에서 사용 중인 여러 파일에 대 한 "AuxPath" 및 "ProjName"를 포함할 수 있습니다.  
  
-   "AuxPath" 문자열에 그 안에 따옴표를 사용할 수 없습니다. 구분 기호로 그 주위에 따옴표가 있을 수 (예를 들어, 큰따옴표 쌍 수 나타내는 데 사용할 빈 문자열)입니다. IDE에서는 MSSCCPRJ에서 읽으면 "AuxPath" 문자열에서 따옴표를 제거 합니다. SCC 파일입니다.  
  
-   MSSCCPRJ "ProjName" 문자열입니다. SCC 파일에서 반환 된 문자열과 정확히 일치 해야 합니다는 `SccGetProjPath` 함수입니다. 함수에서 반환 되는 문자열에 경우 문자열에는 MSSCCPRJ 그 주위에 따옴표 합니다. SCC 파일에는 따옴표 있어야 합니다. 그 반대의 주위에 있습니다.  
  
-   MSSCCPRJ 합니다. SCC 파일을 만들거나 소스 제어에서 파일을 배치할 될 때마다 업데이트 됩니다.  
  
-   MSSCCPRJ 경우입니다. SCC 파일 삭제, 공급자를 다시 생성 해야 그 다음에 해당 디렉터리와 관련 된 소스 제어 작업을 수행 합니다.  
  
-   MSSCCPRJ 합니다. SCC 파일 엄격 하 게 정의 된 형식을 따라야 합니다.  
  
## <a name="an-illustration-of-the-mssccprjscc-file-format"></a>MSSCCPRJ 보여 줍니다. SCC 파일 형식  
 다음은 샘플은 MSSCCPRJ입니다. SCC 파일 형식 (줄 번호를 가이드로만 제공 및 파일 본문에 포함 되지 않아야):  
  
 [줄: 1] `SCC = This is a Source Code Control file`  
  
 [2 번 줄]  
  
 [3 번 줄] `[TestApp.sln]`  
  
 [Line 4] `SCC_Aux_Path = "\\server\vss\"`  
  
 [Line 5] `SCC_Project_Name = "$/TestApp"`  
  
 [Line 6]  
  
 [Line 7] `[TestApp.csproj]`  
  
 [Line 8] `SCC_Aux_Path = "\\server\vss\"`  
  
 [줄 9] `SCC_Project_Name = "$/TestApp"`  
  
 첫 번째 줄은 파일의 용도 설명 하 고이 형식의 모든 파일에 대 한 서명으로 서비스 합니다. 이 줄이 모든 MSSCCPRJ 똑같이 표시 됩니다. SCC 파일:  
  
 `SCC = This is a Source Code Control file`  
  
 파일 이름이 대괄호 안에 표시 된 각 파일에 대 한 설정의 한 섹션에는 다음 합니다. 이 섹션은 추적 중인 각 파일에 대해 반복 됩니다. 즉,이 줄은 파일 이름, 샘플 `[TestApp.csproj]`합니다. IDE는 다음 두 줄을 예상합니다. 하지만 정의 된 값의 스타일 정의 되지 않습니다. 변수는 `SCC_Aux_Path` 및 `SCC_Project_Name`합니다.  
  
 `SCC_Aux_Path = "\\server\vss\"`  
  
 `SCC_Project_Name = "$/TestApp"`  
  
 이 섹션 끝 구분 문자가 있습니다. 이름으로 파일을 파일에 나타나는 모든 리터럴은 scc.h 헤더 파일에 정의 됩니다. 자세한 내용은 참조 [소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [소스 제어 플러그 인을 찾기 위한 키로 사용되는 문자열](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)