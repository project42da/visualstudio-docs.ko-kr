---
title: "IDE에 의해 구현 되는 콜백 함수 | Microsoft Docs"
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
  - "소스 제어 플러그 인, 콜백 함수"
  - "콜백 함수, 소스 제어 플러그 인"
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
caps.latest.revision: 24
caps.handback.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
---
# IDE에 의해 구현 되는 콜백 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

와 통합 하 고 통합 된 최종 사용자 환경을 제공 하기 위해 최대한 매끄러운 통합된 개발 환경 \(IDE\) 소스 제어 플러그 인 사용할 수 IDE에 의해 구현 되는 콜백 함수입니다. 플러그 인 수 이러한 함수를 호출할 소스 제어 작업을 IDE;에 정보를 전달 하는 동안 적절 한 시간에 그런 다음 IDE 네이티브 UI에 포함 된 요소와이 정보를 표시할 수 있습니다. 사용자에 게이 시나리오 경우 플러그 인 사용 자체 UI 보다 덜 조각난된 환경.  
  
 필수 헤더 파일은 scc.h. 기본 위치는 \\Program Files\\VSIP 8.0\\EnvSDK\\common\\inc\\ 합니다. 또한 \\Program Files\\VSIP에 소스 제어 플러그 인 예제를가지고 있는 VSIP 폴더에 8.0\\MSSCCI\\ 합니다.  
  
## 단원 내용  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 사용 되는 콜백 함수에 설명 [SccOpenProject](../extensibility/sccopenproject-function.md) 소스 제어 플러그 IDE를 통해 메시지를 표시 합니다.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 사용 되는 콜백 함수에 설명 [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE에 없는 경우 플러그 인을 버전 제어에서 파일의 전체 목록과 같은 소스 제어에만 사용할 수 있는 정보에 액세스할 수 있습니다.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 사용 되는 콜백 함수에 설명 된 [SccQueryChanges](../extensibility/sccquerychanges-function.md) 작업 합니다.  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 사용 되는 콜백 함수에 설명 된 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) 작업 합니다.  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 콜백 함수를 호출 하 여 설정에 대해 설명 된 [SccSetOption](../extensibility/sccsetoption-function.md) IDE에 이름 변경 내용을 다시 통신 하는 플러그 인 소스 제어를 진행할 수 있습니다.  
  
## 관련 단원  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 프로젝트를 엽니다.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 현재 상태에 대 한 파일의 목록을 검사합니다. 또한 사용 하는 `pfnPopulate` 파일에 대 한 조건을 일치 하지 않는 경우 호출자에 게 알리기 위해 함수는 `nCommand`합니다.  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 디렉터리 및 소스 제어 되는 프로젝트 또는 프로젝트 파일의 목록이 있는지 검사 합니다. 각 디렉터리와 파일 이름은 찾을 수는 콜백 함수에 전달 됩니다.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 파일의 목록에 대 한 이름 변경 내용을 검사 합니다. 각 파일 이름에 해당 변경 상태와 함께 콜백 함수에 전달 됩니다.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 다양 한 옵션을 설정합니다. 각 옵션으로 시작 `SCC_OPT_xxx` 에 자체 정의 된 값 집합이 있습니다.  
  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)  
 소스 제어 플러그 인 SDK의 참조 섹션의 내용을 설명합니다.