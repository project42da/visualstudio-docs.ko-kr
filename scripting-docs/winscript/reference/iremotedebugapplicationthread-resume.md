---
title: "IRemoteDebugApplicationThread::Resume | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationThread.Resume
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationThread::Resume"
ms.assetid: ac290861-515d-4f06-b452-3b96f54e538c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationThread::Resume
스레드를 다시 시작 합니다.  
  
## 구문  
  
```  
HRESULT Resume(  
   DWORD*  pdwCount  
);  
```  
  
#### 매개 변수  
 `pdwCount`  
 \[out\] 스레드의 일시 중단 횟수가입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 스레드를 다시 시작 하면이 일시 중단 횟수를 줄입니다.  
  
## 참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)