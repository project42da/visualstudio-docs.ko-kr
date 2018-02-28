---
title: IDebugAsyncOperation::GetResult | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugAsyncOperation.GetResult
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::GetResult
ms.assetid: 56d43365-6b12-4213-a97c-953c40d7b7f6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60181904408010f35fa4d99d182216e665583aab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugasyncoperationgetresult"></a>IDebugAsyncOperation::GetResult
반환 값과 동기 디버그 작업에서 개체 반환 매개 변수를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetResult(  
   HRESULT*    phrResult,  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phrResult`  
 [out] 작업이 완료 되 면 `phrResult` 의 반환 값은 `IDebugSyncOperation::Execute`합니다.  
  
 `ppunkResult`  
 [out] 작업이 완료 되 면 `ppunkResult` 작업에서 반환 하는 개체 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_PENDING`|작업이 완료 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 반환 된 작업이 완료 된 `HRESULT` 개체에서 매개 변수 및 `IDebugSyncOperation::Execute`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)