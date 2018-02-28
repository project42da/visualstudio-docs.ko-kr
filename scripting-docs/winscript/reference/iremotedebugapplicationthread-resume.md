---
title: IRemoteDebugApplicationThread::Resume | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.Resume
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::Resume
ms.assetid: ac290861-515d-4f06-b452-3b96f54e538c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 265c0a368fc7f0a5faf3ced3f335b3d7d49c1b24
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadresume"></a>IRemoteDebugApplicationThread::Resume
스레드를 다시 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Resume(  
   DWORD*  pdwCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwCount`  
 [out] 스레드 일시 중단 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 스레드를 다시 시작 될 때이 일시 중단 횟수를 감소 시킵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)