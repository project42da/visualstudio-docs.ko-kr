---
title: "IDebugAsyncOperation::GetSyncDebugOperation | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugAsyncOperation.GetSyncDebugOperation
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugAsyncOperation::GetSyncDebugOperation"
ms.assetid: ff89a3bc-57d7-4cb9-9818-8d73ed71af73
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAsyncOperation::GetSyncDebugOperation
이 개체와 관련 된 동기 디버그 작업을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetSyncDebugOperation(  
   IDebugSyncOperation**  ppsdo  
);  
```  
  
#### 매개 변수  
 `ppsdo`  
 \[out\] 이 개체와 관련 된 동기 디버그 작업입니다.  
  
## 반환 값  
 Metoda vrátí `HRESULT`.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|Value|Description|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## 설명  
 이 메서드는이 개체와 관련 된 동기 디버그 작업을 반환 합니다.  
  
## 참고 항목  
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)