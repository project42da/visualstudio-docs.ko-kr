---
title: "IDebugSyncOperation::InProgressAbort | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugSyncOperation.InProgressAbort
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugSyncOperation::InProgressAbort"
ms.assetid: bfd0889c-b627-4843-b1c6-b6b918f42d61
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSyncOperation::InProgressAbort
진행 중인 다른 스레드에서 작업을 취소합니다.  
  
## 구문  
  
```  
HRESULT InProgressAbort();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|작업을 취소할 수 없습니다.|  
|`E_ABORT`|작업을 완료할 수 없습니다.|  
  
## 설명  
 디버그 프로세스 관리자에서 디버거 스레드가 다른 스레드의 진행 되는 작업을 취소 하려면이 메서드를 호출 합니다.  
  
 경우는 `InProgressAbort` 메서드는 작업을 완료할 수 없습니다, 반환 `E_ABORT` 최대한 빨리.  이 메서드를 반환할 수 있습니다 `E_NOTIMPL` 작업을 취소 하는 경우.  
  
## 참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)