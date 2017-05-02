---
title: "IRemoteDebugApplicationEvents::OnBreakFlagChange | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationEvents.OnBreakFlagChange
apilocation: jscript.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationEvents::OnBreakFlagChange"
ms.assetid: 25684454-a0d8-47e0-85f5-2217069a9f45
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationEvents::OnBreakFlagChange
Break 플래그를 변경할 때 이벤트를 처리 합니다.  
  
## 구문  
  
```  
HRESULT OnBreakFlagChange(  
   APPBREAKFLAGS                   abf,  
   IRemoteDebugApplicationThread*  prdatSteppingThread  
);  
```  
  
#### 매개 변수  
 `abf`  
 \[in\] 응용 프로그램에 대 한 현재 중단 플래그입니다.  
  
 `prdatSteppingThread`  
 \[in\] 현재 실행 중인 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 중단 플래그를 변경 하면 이벤트를 처리 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplicationEvents 인터페이스](../../winscript/reference/iremotedebugapplicationevents-interface.md)   
 [APPBREAKFLAGS 열거형](../../winscript/reference/appbreakflags-enumeration.md)