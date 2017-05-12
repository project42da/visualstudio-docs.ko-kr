---
title: "IRemoteDebugApplicationThread::SetNextStatement | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationThread.SetNextStatement
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationThread::SetNextStatement"
ms.assetid: 356766da-f7b7-4e8d-b4f3-2ab8da0609b8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationThread::SetNextStatement
지정 된 프레임의 컨텍스트 내에서 코드를 지정 된 컨텍스트를 최대한 가깝게 계속 강제로 실행.  
  
## 구문  
  
```  
HRESULT SetNextStatement(  
   IDebugStackFrame*   pStackFrame,  
   IDebugCodeContext*  pCodeContext  
);  
```  
  
#### 매개 변수  
 `pStackFrame`  
 \[in\] 스택 프레임 개체입니다.  이 인수는 현재 스택 프레임을 사용 해야 하는 것을 의미 하는 NULL을 수 있습니다.  
  
 `pCodeContext`  
 \[in\] 코드 컨텍스트입니다.  이 인수는 현재 코드 컨텍스트를 의미 하는 NULL을 수 있습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드를 코드에서 지정 된 컨텍스트를 최대한 가깝게 계속 실행 하도록 `pCodeContext`에서 지정한 프레임의 컨텍스트에서 `pStackFrame`.  이러한 인수 중 하나가 될 수 있습니다 `NULL`, 현재 프레임 또는 컨텍스트를 나타내는.  
  
## 참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)