---
title: IDebugProcess2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::Attach
helpviewer_keywords: IDebugProcess2::Attach
ms.assetid: 40d78417-fde2-45c3-96c9-16e06bd9008d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 47b14c3de6b5b9980e2ad420596a1243e84c8882
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2attach"></a>IDebugProcess2::Attach
세션 디버그 관리자 (SDM) 프로세스에 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   GUID*                 rgguidSpecificEngines,  
   DWORD                 celtSpecificEngines,  
   HRESULT*              rghrEngineAttach  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback,  
   Guid[]               rgguidSpecificEngines,  
   uint                 celtSpecificEngines,  
   int[]                rghrEngineAttach  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버그 이벤트 알림에 사용 되는 개체입니다.  
  
 `rgguidSpecificEngines`  
 [in] 배열 하는 프로세스에서 실행 중인 프로그램을 디버깅 하는 데 사용할 디버그 엔진의 Guid입니다. 이 매개 변수에 null 값이 될 수 있습니다. 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `celtSpecificEngines`  
 [in] 디버그 수 있는 엔진은 `rgguidSpecificEngines` 배열과의 크기는 `rghrEngineAttach` 배열입니다.  
  
 `rghrEngineAttach`  
 [out에서] 디버그 엔진에서 반환 된 HRESULT 코드의 배열입니다. 에 지정 된이 배열의 크기는 `celtSpecificEngines` 매개 변수입니다. 각 코드는 일반적으로 하나 `S_OK` 또는 `S_ATTACH_DEFERRED`합니다. 후자는 DE 현재 프로그램에 연결 되어 있는지 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서 가능한 다른 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|지정된 된 프로세스 디버거가 이미 연결 되어 있습니다.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Attach는 동안 보안 위반이 발생 했습니다.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|데스크톱 프로세스 디버거에 연결할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 에 지정 된 디버그 엔진 (DE) 하 여 디버깅할 수 있는 해당 프로세스에서 실행 되는 모든 프로그램은 SDM 연결 프로세스에 연결 하는 `rgguidSpecificEngines` 배열입니다. 설정의 `rgguidSpecificEngines` 매개 변수를 null로 값 또는 포함 `GUID_NULL` 배열의 프로세스의 모든 프로그램에 연결 합니다.  
  
 프로세스에서 발생 하는 모든 디버그 이벤트에 게 보내집니다는 주어진 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 개체입니다. 이 `IDebugEventCallback2` 개체는 SDM이이 메서드를 호출할 때 제공 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)