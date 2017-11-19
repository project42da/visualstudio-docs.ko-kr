---
title: IRemoteDebugApplicationThread::GetState | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IRemoteDebugApplicationThread.GetState
apilocation: pdm.dll
helpviewer_keywords: IRemoteDebugApplicationThread::GetState
ms.assetid: 44503a78-efa9-4fbf-98be-a5dcfa329c5a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce34fa73f97b92d08193c697e991c9e922ac17ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadgetstate"></a>IRemoteDebugApplicationThread::GetState
이 스레드의 상태를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetState(  
   DWORD*  pState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pState`  
 [out] 스레드 상태 플래그의 조합:  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|THREAD_STATE_RUNNING|0x00000001|스레드가 실행 중입니다.|  
|THREAD_STATE_SUSPENDED|0x00000002|스레드가 일시 중단 됩니다.|  
|THREAD_BLOCKED|0x00000004|스레드가 차단 됩니다.|  
|THREAD_OUT_OF_CONTEXT|0x00000008|스레드가 콘텐츠를 벗어났습니다.|  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는이 스레드의 상태를 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)