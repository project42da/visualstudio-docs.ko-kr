---
title: "MSSCCPRJ 합니다. SCC 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인, MSSCCPRJ 합니다. SCC 파일"
  - "MSSCCPRJ 합니다. SCC 파일"
ms.assetid: 6f2e39d6-b79d-407e-976f-b62a3cedd378
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# MSSCCPRJ 합니다. SCC 파일
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 솔루션 또는 프로젝트는 IDE를 사용 하 여 소스 제어에 배치 되 면 IDE 문자열의 형태로 플러그 인 소스 제어에서 두 가지 중요 정보를 받습니다. "AuxPath" 및 "ProjName" 이러한 문자열은 불분명 IDE에는 있지만 사용 플러그 인에서 버전 제어에서 솔루션 또는 프로젝트를 찾을 수 있습니다. IDE 일반적으로 이러한 문자열이 처음으로 호출 하 여 가져옵니다는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md), 솔루션 또는 프로젝트 파일에 대 한 이후 호출에서 다음 저장 하 고는 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다. 솔루션 및 프로젝트 파일에 포함 된, "AuxPath" 및 "ProjName" 문자열은 자동으로 업데이트 되지 사용자 분기를 분기를 만들거나 버전 제어에 있는 솔루션 및 프로젝트 파일을 복사 합니다. 솔루션 및 프로젝트 파일 버전 제어에서의 올바른 위치를 가리키는지 확인 하려면 사용자가 문자열을 수동으로 업데이트 해야 합니다. 문자열은 불투명 하 게 표시 하기 위한 것, 때문에 하지 항상 것은 명확 업데이트 방법을 합니다.  
  
 소스 제어 플러그 인은 MSSCCPRJ 라는 특수 파일에 "AuxPath" 및 "ProjName" 문자열을 저장 하 여이 문제를 방지할 수 있습니다. SCC 파일입니다. 소유 하 고 플러그 인에서 유지 관리는 로컬, 클라이언트 쪽 파일입니다. 이 파일은 소스 제어 되지 만들었으나 소스 제어 파일을 포함 하는 모든 디렉터리에 대 한 플러그 인에 의해 생성 됩니다. 어떤 파일은 Visual Studio 솔루션 및 프로젝트 파일을 확인 하려면 소스 제어 플러그 인 표준 또는 사용자가 제공한 목록에 대해 파일 확장명을 비교할 수 있습니다. IDE는 플러그 인을 지원 하는지는 MSSCCPRJ 감지 합니다. SCC 파일을 더 이상 "AuxPath"를 포함 하 고 솔루션 및 프로젝트 파일에 "ProjName" 문자열은 MSSCCPRJ에서 이러한 문자열을 읽습니다. SCC 파일 대신 합니다.  
  
 소스 제어 플러그 인을 지 원하는 MSSCCPRJ 합니다. SCC 파일은 다음 지침을 따라야 합니다.  
  
-   하나의 MSSCCPRJ 하나만 있을 수 있습니다. 디렉터리 당 SCC 파일입니다.  
  
-   MSSCCPRJ 합니다. SCC 파일 내 지정된 된 디렉터리에서 소스 제어 아래에 있는 여러 파일에 대 한 "AuxPath" 및 "ProjName"를 포함할 수 있습니다.  
  
-   "AuxPath" 문자열에 그 안에 따옴표를 사용할 수 없습니다. 구분 기호로 그 주위에 따옴표를 허용 됩니다 \(예를 들어, 큰따옴표 쌍 수 나타내는 데 사용할 빈 문자열\)입니다. IDE에서는 MSSCCPRJ에서 읽을 때 "AuxPath" 문자열에서 모든 따옴표를 제거 합니다. SCC 파일입니다.  
  
-   MSSCCPRJ "ProjName" 문자열입니다. SCC 파일에서 반환 된 문자열과 정확히 일치 해야는 `SccGetProjPath` 함수입니다. 문자열에 있는 경우 함수에서 반환 된 문자열에는 MSSCCPRJ 그 주위에 따옴표입니다. SCC 파일 따옴표 있어야 주위에 이동 하 고 그 반대의 경우도 마찬가지입니다.  
  
-   MSSCCPRJ 합니다. SCC 파일을 만들거나 소스 제어에서 파일을 배치할 될 때마다 업데이트 됩니다.  
  
-   MSSCCPRJ 면 합니다. SCC 파일 삭제, 공급자를 다시 생성 해야 그 다음에 해당 디렉터리와 관련 된 소스 제어 작업을 수행 합니다.  
  
-   MSSCCPRJ 합니다. SCC 파일 엄격 하 게 정의 된 형식을 따라야 합니다.  
  
## MSSCCPRJ 보여 줍니다. SCC 파일 형식  
 다음은 샘플은 MSSCCPRJ입니다. SCC 파일 형식 \(줄 번호를 가이드로만 제공 하 고 파일 본문에 포함 안\):  
  
 \[줄: 1\] `SCC = This is a Source Code Control file`  
  
 \[입력\]  
  
 \[3 번 줄\] `[TestApp.sln]`  
  
 \[Line 4\] `SCC_Aux_Path = "\\server\vss\"`  
  
 \[줄 5\] `SCC_Project_Name = "$/TestApp"`  
  
 \[6 번 줄\]  
  
 \[7 번 줄\] `[TestApp.csproj]`  
  
 \[Line 8\] `SCC_Aux_Path = "\\server\vss\"`  
  
 \[Line 9\] `SCC_Project_Name = "$/TestApp"`  
  
 첫 번째 줄 파일의 용도 설명 하 고 역할을이 형식의 모든 파일에 대 한 서명입니다. 이 줄이 모든 MSSCCPRJ 똑같이 표시 됩니다. SCC 파일:  
  
 `SCC = This is a Source Code Control file`  
  
 다음은 대괄호로 파일 이름으로 표시 된 각 파일에 대 한 설정의 섹션입니다. 이 섹션은 추적 되 고 각 파일에 대해 반복 됩니다. 즉,이 줄은 파일 이름, 샘플 `[TestApp.csproj]`합니다. IDE는 다음 두 줄이 필요합니다. 하지만 정의 된 값의 스타일을 정의 되지 않습니다. 변수는 `SCC_Aux_Path` 및 `SCC_Project_Name`합니다.  
  
 `SCC_Aux_Path = "\\server\vss\"`  
  
 `SCC_Project_Name = "$/TestApp"`  
  
 이 섹션 끝 구분 문자가 있습니다. 이름으로 파일을 파일에 나타나는 모든 리터럴을 scc.h 헤더 파일에 정의 됩니다. 자세한 내용은 [소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)을 참조하십시오.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)