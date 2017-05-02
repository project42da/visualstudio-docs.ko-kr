---
title: "IDebugAsyncOperation::GetResult | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugAsyncOperation.GetResult
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugAsyncOperation::GetResult"
ms.assetid: 56d43365-6b12-4213-a97c-953c40d7b7f6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAsyncOperation::GetResult
반환 값 및 동기 디버그 작업에서 반환 되는 개체 매개 변수를 제공합니다.  
  
## 구문  
  
```  
HRESULT GetResult(  
   HRESULT*    phrResult,  
   IUnknown**  ppunkResult  
);  
```  
  
#### 매개 변수  
 `phrResult`  
 \[out\] 작업이 완료 된 경우 `phrResult` 의 반환 값이 `IDebugSyncOperation::Execute`.  
  
 `ppunkResult`  
 \[out\] 작업이 완료 된 경우 `ppunkResult` 작업에서 반환 되는 개체 매개 변수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_PENDING`|작업이 완료 되지 않았습니다.|  
  
## 설명  
 작업이 완료 된 경우이 메서드는 반환 된 `HRESULT` 매개 변수에서 개체 및 `IDebugSyncOperation::Execute`.  
  
## 참고 항목  
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)