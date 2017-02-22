---
title: "소스 제어 플러그 인 API 함수 | Microsoft Docs"
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
  - "소스 제어 플러그 인, 함수"
ms.assetid: 4b0536dd-4f92-4ef2-9031-4548281f37aa
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 플러그 인 API 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API에는이 API에 따라 플러그 인 소스 컨트롤에 의해 구현 되어야 하는 다음과 같은 함수를 제공 합니다. 비트 플래그와 연결 된 각 함수와 의미 체계의 서명 및 다른 매개 변수는이 문서에 자세히 설명 되어 있습니다.  
  
## 초기화 및 정리 작업 기능  
  
|함수|설명|  
|--------|--------|  
|[SccCloseProject](../extensibility/scccloseproject-function.md)|프로젝트를 닫습니다.|  
|[SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)|지정한 명령에 대 한 고급 옵션에 대 한 사용자 메시지를 표시합니다.|  
|[SccGetVersion](../extensibility/sccgetversion-function.md)|플러그 인 소스 제어의 버전을 반환 합니다.|  
|[SccInitialize](../extensibility/sccinitialize-function.md)|소스 제어를 플러그 인을 초기화합니다. 플러그 인의 각 인스턴스에 대해 한 번씩 호출 됩니다.|  
|[SccOpenProject](../extensibility/sccopenproject-function.md)|프로젝트를 엽니다.|  
|[SccSetOption](../extensibility/sccsetoption-function.md)|다양 한 옵션을 설정 하는 데 사용 되는 제네릭 함수입니다. 각 옵션으로 시작 `SCC_OPT_xxx` 에 자체 정의 된 값 집합이 있습니다.|  
|[SccUninitialize](../extensibility/sccuninitialize-function.md)|전원 사용 되지 소스 제어 플러그 인 필요로 하는 경우 한 번만 호출 합니다.|  
  
## 핵심 소스 제어 기능  
  
|함수|설명|  
|--------|--------|  
|[SccAdd](../extensibility/sccadd-function.md)|소스 제어 시스템에 대 한 정규화 된 경로 이름으로 지정 된 파일의 배열을 추가 합니다.|  
|[SccAddFromScc](../extensibility/sccaddfromscc-function.md)|소스 제어 시스템에 이미 있는 파일을 찾을 수 있도록 하 고 현재 프로젝트 부분에서는 이러한 파일을 확인 합니다.|  
|[SccCheckin](../extensibility/scccheckin-function.md)|파일의 배열에서 확인합니다.|  
|[SccCheckout](../extensibility/scccheckout-function.md)|체크 아웃 파일의 배열입니다.|  
|[SccDiff](../extensibility/sccdiff-function.md)|소스 제어에서 사용 중인 버전 및 정규화 된 경로 이름에 지정 된 로컬 사용자의 파일 간의 차이점을 보여 줍니다.|  
|[SccGet](../extensibility/sccget-function.md)|파일 집합의 읽기 전용 복사본을 검색 합니다.|  
|[SccGetEvents](../extensibility/sccgetevents-function.md)|호출자가 대답을 소개 하는 파일의 상태를 검사 \(통해 `SccQueryInfo`\).|  
|[SccGetProjPath](../extensibility/sccgetprojpath-function.md)|소스 제어 플러그 인에 의미가 있는 프로젝트 경로 대 한 사용자에 게 묻는 플러그 하면 됩니다.|  
|[SccHistory](../extensibility/scchistory-function.md)|정규화 된 로컬 파일 이름 배열에 대 한 기록을 표시합니다.|  
|[SccPopulateList](../extensibility/sccpopulatelist-function.md)|현재 상태에 대 한 파일의 목록을 검사합니다. 또한 사용 하는 `pfnPopulate` 파일에 대 한 조건을 일치 하지 않는 경우 호출자에 게 알리기 위해 함수는 `nCommand`합니다.|  
|[SccProperties](../extensibility/sccproperties-function.md)|정규화 된 파일의 속성을 보여 줍니다.|  
|[SccQueryInfo](../extensibility/sccqueryinfo-function.md)|현재 상태에 대 한 정규화 된 파일의 목록이 있는지 검사합니다.|  
|[SccRemove](../extensibility/sccremove-function.md)|소스 제어 시스템에서 정규화 된 파일의 배열을 제거합니다.|  
|[SccRename](../extensibility/sccrename-function.md)|소스 제어 시스템에서 지정된 된 파일을을 새 이름 이름을 바꿉니다.|  
|[SccRunScc](../extensibility/sccrunscc-function.md)|다양 한 소스 제어 시스템의 기능에 액세스합니다.|  
|[SccUncheckout](../extensibility/sccuncheckout-function.md)|파일의 배열의 체크 아웃 실행 취소합니다.|  
  
## 지 원하는 추가 기능 \(소스 제어 플러그 인 API 버전 1.2\) 함수  
 이 그룹의 함수 버전 1.2의 소스 제어 플러그 인 API에에서 포함 된 추가 기능을 정의 합니다. 고급 소스 제어 기능 및 기능에 대 한 액세스를 제공합니다.  
  
|함수|설명|  
|--------|--------|  
|[SccBeginBatch](../extensibility/sccbeginbatch-function.md)|일괄 처리 작업을 시작합니다.|  
|[SccCreateSubProject](../extensibility/scccreatesubproject-function.md)|기존 부모 프로젝트에서 지정한 이름을 가진 하위 프로젝트를 만듭니다.|  
|[SccDirDiff](../extensibility/sccdirdiff-function.md)|정규화 된 경로 이름 및 소스 제어 데이터베이스 위치에 지정 된 로컬 사용자의 디렉터리 간의 차이점을 보여 줍니다.|  
|[SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)|현재 상태에 대 한 정규화 된 디렉터리의 목록이 있는지 검사합니다.|  
|[SccEndBatch](../extensibility/sccendbatch-function.md)|일괄 처리 작업을 끝냅니다.|  
|[SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md)|지정된 된 프로젝트 \(프로젝트 존재 해야 함\)의 경로 parent가 반환 되었습니다.|  
|[SccIsMultiCheckoutEnabled](../extensibility/sccismulticheckoutenabled-function.md)|파일에 여러 체크 아웃 허용 되는지 여부를 확인 합니다.|  
|[SccWillCreateSccFile](../extensibility/sccwillcreatesccfile-function.md)|플러그 인은 만들 있는지 MSSCCPRJ 확인 합니다. SCC 파일입니다.|  
  
## 함수를 지 원하는 고급 기능 \(소스 제어 플러그 인 API의 버전 1.3\)  
 이 그룹의 함수 버전 1.3의 소스 제어 플러그 인 API에에서 포함 된 추가 기능을 정의 합니다. 고급 소스 제어 기능 및 기능에 대 한 액세스를 제공합니다.  
  
|함수|설명|  
|--------|--------|  
|[SccAddFilesFromSCC](../extensibility/sccaddfilesfromscc-function.md)|소스 제어에서 파일 목록의 현재 프로젝트에 추가합니다.|  
|[SccBackgroundGet](../extensibility/sccbackgroundget-function.md)|사용자 인터페이스 없이 소스 제어에서 파일의 목록을 검색합니다.|  
|[SccEnumChangedFiles](../extensibility/sccenumchangedfiles-function.md)|로컬 파일의 다른 소스 제어에서 파일의 목록을 검색 합니다.|  
|[SccGetExtendedCapabilities](../extensibility/sccgetextendedcapabilities-function.md)|소스 제어 플러그 인에서 지 원하는 확장된 기능을 지정 하는 플래그를 검색 합니다.|  
|[SccGetUserOption](../extensibility/sccgetuseroption-function.md)|사용자 고유의 옵션을 검색합니다.|  
|[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)|디렉터리 및 소스 제어 되는 프로젝트 또는 프로젝트 파일의 목록이 있는지 검사 합니다. 각 디렉터리와 파일 이름은 찾을 수는 콜백 함수에 전달 됩니다.|  
|[SccQueryChanges](../extensibility/sccquerychanges-function.md)|이름을 변경한 파일의 목록에 검사 합니다. 각 파일 이름은 해당 변경 상태와 함께 콜백 함수에 전달 됩니다.|  
  
## 요구 사항  
 헤더: scc.h  
  
 \(환경 SDK에 제공 된 공통 폴더는 기본적으로 포함 *\[드라이브\]*\\Program Files\\VSIP 8.0\\EnvSDK\\common\\inc; MSSCCI 샘플을 사용 하 여 VSIP 폴더에도 제공 된 *\[드라이브\]*\\Program Files\\VSIP 8.0\\MSSCCI\).  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [소스 제어 플러그 인 만들기](../extensibility/internals/creating-a-source-control-plug-in.md)