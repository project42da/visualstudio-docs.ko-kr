---
title: "SccSetOption 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccSetOption"
helpviewer_keywords: 
  - "SccSetOption 함수"
ms.assetid: 4b5e6666-c24c-438a-a9df-9c52f58f8175
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# SccSetOption 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 플러그 인의 동작을 제어 하는 옵션을 설정 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccSetOption(  
   LPVOID pvContext,  
   LONG   nOption,  
   LONG   dwVal  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nOption  
 \[in\] 설정 되는 옵션입니다.  
  
 dwVal  
 \[in\] 옵션에 대 한 설정입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|옵션 설정 되었습니다.|  
|SCC\_I\_SHARESUBPROJOK|반환 된 경우 `nOption` 가 `SCC_OPT_SHARESUBPROJ` 소스 제어 플러그 인 IDE 대상 폴더를 설정할 수 있습니다.|  
|SCC\_E\_OPNOTSUPPORTED|옵션을 설정 하지 않았습니다 및 해야 사용할 수 없습니다.|  
  
## 설명  
 IDE에서 소스 제어 플러그 인의 동작을 제어 하려면이 함수를 호출 합니다. 첫 번째 매개 변수 `nOption`, 두 번째 동안 설정 되는 값을 나타내는 `dwVal`, 해당 값을 가진 수행할 작업을 나타냅니다. 플러그 인 연결 된이 정보를 저장 한 `pvContext``,` IDE 호출한 후이 함수를 호출 해야 하므로 [SccInitialize](../extensibility/sccinitialize-function.md) \(각 호출 후 반드시는 [SccOpenProject](../extensibility/sccopenproject-function.md)\).  
  
 요약 정보 옵션 및 해당 값입니다.  
  
|`nOption`|`dwValue`|설명|  
|---------------|---------------|--------|  
|`SCC_OPT_EVENTQUEUE`|`SCC_OPT_EQ_DISABLE`<br /><br /> `SCC_OPT_EQ_ENABLE`|이벤트 큐 백그라운드 하는 설정 하거나 해제 합니다.|  
|`SCC_OPT_USERDATA`|임의 값|에 전달할 사용자 값을 지정 된 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) 콜백 함수입니다.|  
|`SCC_OPT_HASCANCELMODE`|`SCC_OPT_HCM_NO`<br /><br /> `SCC_OPT_HCM_YES`|지원 하는지 여부를 IDE 현재 작업 취소를 나타냅니다.|  
|`SCC_OPT_NAMECHANGEPFN`|에 대 한 포인터는 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) 콜백 함수|이름 변경 콜백 함수에 대 한 포인터를 설정합니다.|  
|`SCC_OPT_SCCCHECKOUTONLY`|`SCC_OPT_SCO_NO`<br /><br /> `SCC_OPT_SCO_YES`|수동으로 \(소스 제어 사용자 인터페이스를 통해\) 해당 파일을 확인 하거나 여부은 체크 아웃 해야 소스 제어 플러그 인을 통해서만 IDE를 사용 하는지 여부를 나타냅니다.|  
|`SCC_OPT_SHARESUBPROJ`|N\/A|로컬 프로젝트 폴더를 지정 하는 IDE를 허용 하는 소스 제어 플러그 인 경우 플러그 인 반환 `SCC_I_SHARESUBPROJOK`합니다.|  
  
## SCC\_OPT\_EVENTQUEUE  
 경우 `nOption` 은 `SCC_OPT_EVENTQUEUE`, IDE는 사용 하지 않도록 설정 \(또는 다시 활성화\) 백그라운드 작업을 처리 합니다. 예를 들어, IDE는 컴파일 중 소스 제어 플러그 어떠한 종류의 유휴에 처리를 중지 하려면 지시할 수 있습니다. 컴파일 후 다시 이벤트 큐에 대 한 플러그 인을 최신 상태로 유지 하는 백그라운드 처리를 수입니다. 에 해당 하는 `SCC_OPT_EVENTQUEUE` 값 `nOption`, 에 대 한 두 개의 가능한 값은 `dwVal`, 즉, `SCC_OPT_EQ_ENABLE` 및 `SCC_OPT_EQ_DISABLE`합니다.  
  
## SCC\_OPT\_HASCANCELMODE  
 경우에 대 한 값 `nOption` 은 `SCC_OPT_HASCANCELMODE`, IDE 장기 작업을 취소할 수 있습니다. 설정 `dwVal` 를 `SCC_OPT_HCM_NO` \(기본값\) IDE 취소 모드 없음 있음을 나타냅니다. 소스 제어 플러그 인 사용자를 취소할 수를 만들려고 하는 경우 자체 취소 단추를 제공 해야 합니다.`SCC_OPT_HCM_YES` IDE 소스 코드 제어 플러그 인 자체 취소 단추를 표시 하지 않아도 되므로 작업을 취소 하는 기능을 제공 함을 나타냅니다. IDE 설정 하는 경우 `dwVal` 를 `SCC_OPT_HCM_YES`, 에 응답 하도록 준비 되 면 `SCC_MSG_STATUS` 및 `DOCANCEL` 로 전송 된 메시지는 `lpTextOutProc` 콜백 함수 \(참조 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)\). IDE는이 변수를 설정 하지 않으면, 플러그 인 보내면 안 두 메시지입니다.  
  
## SCC\_OPT\_NAMECHANGEPFN  
 NOption로 설정 되어 있으면 `SCC_OPT_NAMECHANGEPFN`, 및 원본 제어 플러그 인 및 IDE 허용, 플러그 인 수 실제로 이름 바꾸기 또는 소스 제어 작업을 하는 동안 파일을 이동 합니다.`dwVal` 함수 포인터 형식으로 설정 됩니다 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)합니다. 소스 제어 작업을 하는 동안 플러그 인 수이 함수를 호출, 세 개의 매개 변수를 전달 합니다. 이 IDE와 관련 된 정보에 대 한 포인터 및 해당 파일의 새 이름 \(정규화 된 경로로\) 파일의 이전 이름 \(정규화 된 경로로\)입니다. IDE를 호출 하 여이 마지막 포인터에 보내는 `SccSetOption` 와 `nOption` 로 설정 `SCC_OPT_USERDATA`, 와 `dwVal` 된 데이터를 가리키는 합니다. 이 함수에 대 한 지원을 선택 사항입니다. VSSCI 플러그 인을 사용 하 여가이 기능 초기화 해야 해당 함수 포인터와 사용자 데이터 변수를 `NULL`, 것 부여 되어 하나 rename 함수를 호출 하지 해야 합니다. 지정 된 값을 유지 하거나 새 호출에 대 한 응답에서 변경 하려면에 대비해 야 `SccSetOption`합니다. 소스 제어 명령 작업 중에 발생 하지 않을 수 있지만 명령 간에 발생할 수 있습니다.  
  
## SCC\_OPT\_SCCCHECKOUTONLY  
 NOption로 설정 되어 있으면 `SCC_OPT_SCCCHECKOUTONLY`, IDE가는 현재 열려 있는 프로젝트의 파일 해야 하지 수 체크 아웃 나타내는 수동으로 소스 제어 시스템의 사용자 인터페이스를 통해. 대신, IDE 제어 플러그 인 소스 제어를 사용할 때만 파일을 체크 해야 합니다. 경우 `dwValue` 로 설정 된 `SCC_OPT_SCO_NO`, 파일 플러그 인에서 정상적으로 처리 되어야 하 고 소스 제어 UI 통해 체크 아웃할 수 있는 것을 의미 합니다. 경우 `dwValue` 로 설정 된 `SCC_OPT_SCO_YES`, 않으면만 플러그 인 허용 파일을 체크 아웃 하 고 소스 제어 시스템의 UI를 호출 하지 않아야 합니다. IDE IDE를 통해 체크 아웃 하는 의미가 있는 "의사 \(pseudo\) 파일이" 할 수 있는 상황입니다.  
  
## SCC\_OPT\_SHARESUBPROJ  
 경우`nOption` 로 설정 된 `SCC_OPT_SHARESUBPROJ`, IDE에서 소스 제어 플러그 인 소스 제어에서 파일을 추가할 때 지정 된 로컬 폴더를 사용할 수 있는지 여부를 테스트 합니다. 값은 `dwVal` 매개 변수는이 경우 중요 하지 않습니다. 플러그 인 파일 원본에서 추가 될 위치는 로컬 대상 폴더를 지정 하는 IDE를 허용 하는 경우 제어는 [SccAddFromScc](../extensibility/sccaddfromscc-function.md) 호출 되는 플러그 인을 반환 해야 합니다 `SCC_I_SHARESUBPROJOK` 때는 `SccSetOption` 함수를 호출 합니다. IDE를 사용 하 여는 `lplpFileNames` 의 매개 변수는 `SccAddFromScc` 대상 폴더에 전달 하는 함수입니다. 플러그 인 추가 소스 제어에서 파일을 해당 대상 폴더를 사용 합니다. 플러그 인 반환 하지 않는 경우 `SCC_I_SHARESUBPROJOK` 때는 `SCC_OPT_SHARESUBPROJ` 옵션 설정, IDE 플러그 임을 가정 현재 로컬 폴더에만 파일을 추가할 수 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccAddFromScc](../extensibility/sccaddfromscc-function.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)   
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)