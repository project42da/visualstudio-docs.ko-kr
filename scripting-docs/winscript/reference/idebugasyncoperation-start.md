---
title: "IDebugAsyncOperation::Start | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugAsyncOperation.Start
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugAsyncOperation::Start"
ms.assetid: a7272364-28e0-48ae-8405-b8bce8a6b9fd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAsyncOperation::Start
비동기 작업이 시작 됩니다.  
  
## 구문  
  
```  
HRESULT Start(  
   IDebugAsyncOperationCallBack*  padocb  
);  
```  
  
#### 매개 변수  
 `padocb`  
 이 작업에서 상태 이벤트를 수신 하는 콜백 인터페이스입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_UNEXPECTED`|이미 작업을 보류 중입니다.|  
  
## 설명  
 이 메서드로 인해 `IDebugSyncOperation::Execute` 에서 가져온 스레드에서 비동기적으로 호출 하려면 `IDebugSyncOperation::GetTargetThread`.  이 메서드는 디버거에서 스레드 내 에서만 호출 되어야 합니다. 그렇지 않으면 작업이 완료 될 때까지 반환 하지 않습니다.  
  
## 참고 항목  
 [IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)   
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)   
 [IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)