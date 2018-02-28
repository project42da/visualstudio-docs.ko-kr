---
title: IRemoteDebugApplicationThread::GetSystemThreadId | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.GetSystemThreadId
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::GetSystemThreadId
ms.assetid: 6a6d5f62-4f60-4e87-9206-3c6f2e026d11
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0082382c5a9d6dc854ed1b7bc9f45b17041b8084
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadgetsystemthreadid"></a>IRemoteDebugApplicationThread::GetSystemThreadId
스레드와 연결 된 운영 체제-종속 식별자를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSystemThreadId(  
   DWORD*  dwThreadId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwThreadId`  
 [out] 스레드와 연결 된 운영 체제-종속 식별자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 값 `dwThreadId` 컴퓨터 전체에서 고유 해야 하는 필요 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)