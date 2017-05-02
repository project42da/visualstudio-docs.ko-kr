---
title: "IDebugAsyncOperation::Abort | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugAsyncOperation.Abort
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugAsyncOperation::Abort"
ms.assetid: 232541c6-81b8-4eb7-96a7-a8e5fe087b31
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAsyncOperation::Abort
작업을 취소 합니다.  
  
## 구문  
  
```  
HRESULT Abort();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|S\_OK|메서드가 성공했으며|  
|E\_NOTIMPL|작업을 취소할 수 없습니다.|  
  
## 설명  
 이 방법은 일반적으로 응답 하지 않는 작업을 취소 하려면 디버거에서 스레드 내에서 호출 됩니다.  이 메서드는 `InProgressAbort` 메서드는 `IDebugSyncOperation` 호출 하는 개체.  
  
## 참고 항목  
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)   
 [IDebugSyncOperation::InProgressAbort](../../winscript/reference/idebugsyncoperation-inprogressabort.md)