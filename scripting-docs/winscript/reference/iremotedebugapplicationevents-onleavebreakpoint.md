---
title: "IRemoteDebugApplicationEvents::OnLeaveBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationEvents.OnLeaveBreakPoint
apilocation: jscript.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationEvents::OnLeaveBreakPoint"
ms.assetid: 00449a23-1f67-4078-ad06-4c426abf7587
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationEvents::OnLeaveBreakPoint
중단점을 두고 이벤트를 처리 합니다.  
  
## 구문  
  
```  
HRESULT OnLeaveBreakPoint(  
   IRemoteDebugApplicationThread*  prdat  
);  
```  
  
#### 매개 변수  
 `prdat`  
 \[in\] 중단점이 왼쪽 응용 프로그램 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 이벤트에 중단점을 두고 처리 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplicationEvents 인터페이스](../../winscript/reference/iremotedebugapplicationevents-interface.md)