---
title: "IDebugSyncOperation::GetTargetThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugSyncOperation.GetTargetThread
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugSyncOperation::GetTargetThread"
ms.assetid: e6eeeb90-b5ed-4727-8434-fa3186c25013
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSyncOperation::GetTargetThread
대상 응용 프로그램 스레드가이 동기 작업을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetTargetThread(  
   IDebugApplicationThread**  ppatTarget  
);  
```  
  
#### 매개 변수  
 `ppatTarget`  
 \[out\] 이 동기화 작업에 대 한 대상 응용 프로그램 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 대상 응용 프로그램 스레드가이 동기 작업을 반환합니다.  
  
## 참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)