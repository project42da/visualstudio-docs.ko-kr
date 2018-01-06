---
title: "IDE에 의해 구현 되는 콜백 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3c1845a82947286800145ff898f8f49f8c3c2477
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions-implemented-by-the-ide"></a>IDE에 의해 구현 되는 콜백 함수
와 통합으로 최대한와 통합 된 최종 사용자 환경을 제공 하기 위해 완벽 한 통합된 개발 환경 (IDE) 소스 제어 플러그 인 사용할 수는 IDE에 의해 구현 되는 콜백 함수입니다. 플러그 인 이러한 함수는 소스 제어 작업; IDE에 정보를 전달 하는 동안 적절 한 시간에 호출할 수 있습니다. 그런 다음 IDE 해당 네이티브 UI에 포함 된 요소와이 정보를 표시할 수 있습니다. 사용자에 게이 시나리오는 플러그 인 사용 자체 UI 경우 보다 덜 조각난된 경험 합니다.  
  
 필수 헤더 파일이 scc.h입니다. 기본 위치는 \Program Files\VSIP 8.0\EnvSDK\common\inc\\합니다. 소스 제어 플러그 인 샘플 \Program Files\VSIP 8.0\MSSCCI에가지고 있는 VSIP 폴더에 이기도\\합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 사용 되는 콜백 함수에 설명 [SccOpenProject](../extensibility/sccopenproject-function.md) IDE를 통해 플러그 인 소스 제어에서 메시지를 표시 합니다.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 사용 되는 콜백 함수에 설명 [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE 없을 경우 소스 제어 플러그 인 버전 제어 중인 파일의 전체 목록은 같은 경우에 사용할 수 있는 정보에 액세스할 수 있습니다.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 사용 되는 콜백 함수에 설명 된 [SccQueryChanges](../extensibility/sccquerychanges-function.md) 작업 합니다.  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 사용 되는 콜백 함수에 설명 된 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) 작업 합니다.  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 호출 하 여 설정 하는 콜백 함수에 설명 된 [SccSetOption](../extensibility/sccsetoption-function.md) 소스 제어 플러그 IDE에 이름이 변경 내용을 다시 통신할 수 있도록 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 프로젝트를 엽니다.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 현재 상태에 대 한 파일 목록에 있는지 검사합니다. 또한 사용 하 여는 `pfnPopulate` 함수를 파일에 대 한 조건을 일치 하지 않는 경우 호출자에 게는 `nCommand`합니다.  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 디렉터리와 하나 이상의 소스 제어에서 사용 중인 프로젝트의 파일 목록을 검사 합니다. 각 디렉터리 및 파일 이름은 찾을 수는 콜백 함수에 전달 됩니다.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 이름이 변경 된 파일의 목록에 내용이 있는지 검사 합니다. 각 파일 이름에 해당 변경 상태와 함께 콜백 함수에 전달 됩니다.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 다양 한 옵션을 설정합니다. 각 옵션으로 시작 `SCC_OPT_xxx` 있으며 자체 정의 된 값 집합이 있습니다.  
  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)  
 소스 제어 플러그 인 SDK의 참조 섹션의 내용에 설명 합니다.