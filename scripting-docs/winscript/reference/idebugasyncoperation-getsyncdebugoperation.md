---
title: IDebugAsyncOperation::GetSyncDebugOperation | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugAsyncOperation.GetSyncDebugOperation
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::GetSyncDebugOperation
ms.assetid: ff89a3bc-57d7-4cb9-9818-8d73ed71af73
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae53dde2b7e48a4bf67cbd7aa5d70904c57d90f2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugasyncoperationgetsyncdebugoperation"></a>IDebugAsyncOperation::GetSyncDebugOperation
이 개체와 관련 된 동기 디버그 작업을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSyncDebugOperation(  
   IDebugSyncOperation**  ppsdo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppsdo`  
 [out] 이 개체와 관련 된 동기 디버그 작업입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는이 개체와 관련 된 동기 디버그 작업을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)