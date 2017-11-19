---
title: "SccSetOption 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccSetOption
helpviewer_keywords: SccSetOption function
ms.assetid: 4b5e6666-c24c-438a-a9df-9c52f58f8175
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a0bc7ab99c6bc3643ee61b403e4aa0c40c41a63a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccsetoption-function"></a>SccSetOption 함수
이 함수는 소스 제어 플러그 인의 동작을 제어 하는 옵션을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccSetOption(  
   LPVOID pvContext,  
   LONG   nOption,  
   LONG   dwVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nOption  
 [in] 설정 되는 옵션입니다.  
  
 dwVal  
 [in] 옵션에 대 한 설정입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|옵션을 설정 했습니다.|  
|SCC_I_SHARESUBPROJOK|경우 반환 되는 `nOption` 가 `SCC_OPT_SHARESUBPROJ` 소스 제어 플러그 인 IDE에서이 대상 폴더를 설정할 수 있습니다.|  
|SCC_E_OPNOTSUPPORTED|옵션을 설정 하지 않았습니다 및에 신뢰할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 IDE의 소스 제어 플러그 인 동작을 제어 하려면이 함수를 호출 합니다. 첫 번째 매개 변수 `nOption`, 설정 되는, 고 두 번째 값을 나타냅니다 `dwVal`, 해당 값으로 수행할 작업을 나타냅니다. 플러그 인에 연결 된이 정보를 저장 한 `pvContext``,` IDE 호출한 후이 함수를 호출 해야 하므로 [SccInitialize](../extensibility/sccinitialize-function.md) (을 호출할 때마다 후 반드시는 [SccOpenProject](../extensibility/sccopenproject-function.md)).  
  
 요약 정보 옵션 및 해당 값입니다.  
  
|`nOption`|`dwValue`|설명|  
|---------------|---------------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|`SCC_OPT_EQ_DISABLE`<br /><br /> `SCC_OPT_EQ_ENABLE`|이벤트 큐 백그라운드 하는 설정/해제 합니다.|  
|`SCC_OPT_USERDATA`|임의의 값|변수에 전달 될 사용자 값을 지정 된 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) 콜백 함수입니다.|  
|`SCC_OPT_HASCANCELMODE`|`SCC_OPT_HCM_NO`<br /><br /> `SCC_OPT_HCM_YES`|지원 하는지 여부를 IDE 현재의 작업 취소를 나타냅니다.|  
|`SCC_OPT_NAMECHANGEPFN`|에 대 한 포인터는 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) 콜백 함수|이름 변경 콜백 함수에 대 한 포인터를 설정합니다.|  
|`SCC_OPT_SCCCHECKOUTONLY`|`SCC_OPT_SCO_NO`<br /><br /> `SCC_OPT_SCO_YES`|IDE 허용 여부은 체크 아웃 해야만 소스 제어 플러그 인을 통해 또는 수동으로 (소스 제어 사용자 인터페이스를 통해) 해당 파일을 검사 하는지 여부를 나타냅니다.|  
|`SCC_OPT_SHARESUBPROJ`|N/A|소스 제어 플러그 인 허용 IDE 로컬 프로젝트 폴더를 지정 하는 경우 플러그 인 반환 `SCC_I_SHARESUBPROJOK`합니다.|  
  
## <a name="sccopteventqueue"></a>SCC_OPT_EVENTQUEUE  
 경우 `nOption` 은 `SCC_OPT_EVENTQUEUE`, IDE가 사용 하지 않도록 설정 (또는 다시 사용 하도록 설정) 백그라운드 작업을 처리 합니다. 예를 들어,를 컴파일하는 동안 IDE 소스 제어 플러그 인을 어떤 종류의 유휴에 처리를 중지를 지시할 수 있습니다. 다시 컴파일, 후 이벤트 큐에 대 한 플러그 인을 최신 상태로 유지 하는 백그라운드 처리를 수입니다. 에 해당 하는 `SCC_OPT_EVENTQUEUE` 값 `nOption`, 두 개의 가능한 값에 대 한 `dwVal`, 즉, `SCC_OPT_EQ_ENABLE` 및 `SCC_OPT_EQ_DISABLE`합니다.  
  
## <a name="sccopthascancelmode"></a>SCC_OPT_HASCANCELMODE  
 경우에 대 한 값 `nOption` 은 `SCC_OPT_HASCANCELMODE`, IDE 장기 작업을 취소할 수 있습니다. 설정 `dwVal` 를 `SCC_OPT_HCM_NO` (기본값) IDE 비 취소 모드에 있는지를 나타냅니다. 소스 제어 플러그 인은 사용자를 취소할 수를 원하는 경우 자체 "취소" 단추가 제공 해야 합니다. `SCC_OPT_HCM_YES`IDE 플러그 인 SCC 자체 "취소" 단추가 표시 하지 않아도 되므로 작업을 취소 하는 기능을 제공 함을 나타냅니다. IDE 설정 하는 경우 `dwVal` 를 `SCC_OPT_HCM_YES`에 응답할 준비가 `SCC_MSG_STATUS` 및 `DOCANCEL` 에 전송 된 메시지는 `lpTextOutProc` 콜백 함수 (참조 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)). IDE에서이 변수를 설정 하는 경우 플러그 인 보내면 안 이러한 두 메시지입니다.  
  
## <a name="sccoptnamechangepfn"></a>SCC_OPT_NAMECHANGEPFN  
 NOption로 설정 되어 있으면 `SCC_OPT_NAMECHANGEPFN`, 및 원본 제어 플러그 인 및 IDE 허용 플러그 인 수을 실제로 이름을 변경 하거나 소스 제어 작업을 하는 동안 파일을 이동 합니다. `dwVal` 함수 포인터 형식으로 설정 됩니다 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)합니다. 소스 제어 작업을 하는 동안 플러그 인 수이 함수를 호출, 세 개의 매개 변수를 전달 합니다. 이 해당 파일 및 IDE와 관련 된 정보에 대 한 포인터의 새 이름 (정규화 된 경로로) 파일의 이전 이름 (정규화 된 경로로)입니다. 호출 하 여이 마지막 포인터에서 IDE 보냅니다 `SccSetOption` 와 `nOption` 로 설정 `SCC_OPT_USERDATA`와 `dwVal` 된 데이터를 가리키는 합니다. 이 함수에 대 한 지원을 선택 사항입니다. VSSCI 플러그-를 사용 하 여가이 기능 초기화 해야 해당 함수 포인터 및 사용자 데이터 변수를 `NULL`, 것 부여 되어 하나 rename 함수를 호출 하지 해야 합니다. 지정 된 값을 보유할 또는에 대 한 새 호출에 대 한 응답의 설정을 변경 하려면에 준비 해야 `SccSetOption`합니다. 소스 제어 명령 작업 중에 발생 하지 않고이 있지만 명령 사이 발생할 수 있습니다.  
  
## <a name="sccoptscccheckoutonly"></a>SCC_OPT_SCCCHECKOUTONLY  
 NOption로 설정 되어 있으면 `SCC_OPT_SCCCHECKOUTONLY`, IDE는 현재 열려 있는 프로젝트의 파일 되지 체크 수동으로 소스 제어 시스템의 사용자 인터페이스를 통해 되었음이 표시 되 합니다. 대신, 파일 체크 IDE 제어 플러그 인 소스 제어를 사용할 때만 합니다. 경우 `dwValue` 로 설정 된 `SCC_OPT_SCO_NO`, 파일 플러그 인에서 정상적으로 처리 되어야 하 고 소스 제어 UI 통해 체크 아웃할 수 있음을 의미 합니다. 경우 `dwValue` 로 설정 된 `SCC_OPT_SCO_YES`다음 플러그만 하도록 허용 된 파일을 체크 아웃 하 고 소스 제어 시스템의 UI를 호출 해서는 안됩니다. 이 IDE IDE를 통해 체크 아웃을 구성 하는 "의사 (pseudo) 파일" 할 수 있는 상황입니다.  
  
## <a name="sccoptsharesubproj"></a>SCC_OPT_SHARESUBPROJ  
 경우`nOption` 로 설정 된 `SCC_OPT_SHARESUBPROJ`, IDE를 소스 제어 플러그 인 소스 제어에서 파일을 추가할 때 지정된 된 로컬 폴더를 사용할 수 있는지 여부를 테스트 합니다. 값은 `dwVal` 매개 변수는이 경우에 중요 하지 않습니다. 플러그 인 허용 IDE 파일 원본에서 추가 될 위치는 로컬 대상 폴더를 지정 하는 경우 제어는 [SccAddFromScc](../extensibility/sccaddfromscc-function.md) 플러그 인을 반환 해야 합니다 라고 `SCC_I_SHARESUBPROJOK` 때는 `SccSetOption` 함수는 호출 됩니다. IDE를 사용 하 여는 `lplpFileNames` 의 매개 변수는 `SccAddFromScc` 대상 폴더에 전달 하는 함수입니다. 플러그 인 추가 소스 제어에서 파일을 배치할 대상 폴더를 사용 합니다. 플러그 인 반환 하지 않는 경우 `SCC_I_SHARESUBPROJOK` 때는 `SCC_OPT_SHARESUBPROJ` 옵션이 설정 되어, IDE 있다고 가정 플러그 인 파일을 현재 로컬 폴더에만 추가할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccAddFromScc](../extensibility/sccaddfromscc-function.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)   
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)