---
title: "IRemoteDebugApplicationThread::GetState | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationThread.GetState
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationThread::GetState"
ms.assetid: 44503a78-efa9-4fbf-98be-a5dcfa329c5a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationThread::GetState
이 스레드의 상태를를 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetState(  
   DWORD*  pState  
);  
```  
  
#### 매개 변수  
 `pState`  
 \[out\] 다음 스레드 상태 플래그의 조합.  
  
|상수|값|설명|  
|--------|-------|--------|  
|THREAD\_STATE\_RUNNING|0x00000001|스레드 실행 중입니다.|  
|THREAD\_STATE\_SUSPENDED|0x00000002|스레드가 일시 중단되었습니다.|  
|THREAD\_BLOCKED|0x00000004|스레드가 차단되었습니다.|  
|THREAD\_OUT\_OF\_CONTEXT|0x00000008|스레드가 부족 콘텐츠입니다.|  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는이 스레드의 상태를를 가져옵니다.  
  
## 참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)