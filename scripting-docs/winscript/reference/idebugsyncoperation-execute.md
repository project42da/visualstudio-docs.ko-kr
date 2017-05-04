---
title: "IDebugSyncOperation::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugSyncOperation.Execute
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugSyncOperation::Execute"
ms.assetid: a45b8c7d-c51a-4098-877f-fbec2f1f6947
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSyncOperation::Execute
동기적으로 작업을 수행 하 고 반환 합니다.  
  
## 구문  
  
```  
HRESULT Execute(  
   IUnknown**  ppunkResult  
);  
```  
  
#### 매개 변수  
 `ppunkResult`  
 \[out\] 작업에서 반환 된 개체 매개 변수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_ABORT`|호출 하 여 작업이 중단 되는 `IDebugSyncOperation::InProgressAbort` 메서드.|  
  
## 설명  
 대상 스레드 호출에서 프로세스 디버그 관리자는 `Execute` 메서드가 동기적으로.  
  
## 참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)