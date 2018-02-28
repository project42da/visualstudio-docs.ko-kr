---
title: IRemoteDebugApplicationThread::SetNextStatement | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.SetNextStatement
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::SetNextStatement
ms.assetid: 356766da-f7b7-4e8d-b4f3-2ab8da0609b8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb23fa643f9a2333e17239a74d0da2f75e1ea791
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadsetnextstatement"></a>IRemoteDebugApplicationThread::SetNextStatement
지정 된 프레임의 컨텍스트에서 지정 된 코드 컨텍스트를 최대한 가깝게 계속 강제로 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetNextStatement(  
   IDebugStackFrame*   pStackFrame,  
   IDebugCodeContext*  pCodeContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 [in] 스택 프레임 개체입니다. 이 인수에는 현재 스택 프레임을 사용 해야 하는 NULL 일 수 있습니다.  
  
 `pCodeContext`  
 [in] 코드 컨텍스트입니다. 이 인수에는 현재 코드 컨텍스트를 사용 해야 하는 NULL 일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 지정 된 코드 컨텍스트를 최대한 가깝게 계속 실행 하면 `pCodeContext`를 지정한 프레임의 컨텍스트에서 `pStackFrame`합니다. 이러한 인수 중 하나가 될 수 있습니다 `NULL`을 현재 프레임 또는 컨텍스트를 나타내는입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)