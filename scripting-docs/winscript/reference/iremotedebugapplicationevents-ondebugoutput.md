---
title: "IRemoteDebugApplicationEvents::OnDebugOutput | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationEvents.OnDebugOutput
apilocation: jscript.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationEvents::OnDebugOutput"
ms.assetid: db08872e-3d84-4d7f-bf94-a851bf43a333
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationEvents::OnDebugOutput
디버거 출력 이벤트를 처리합니다.  
  
## 구문  
  
```  
HRESULT OnDebugOutput(  
   LPCOLESTR  pstr  
);  
```  
  
#### 매개 변수  
 `pstr`  
 \[in\] 디버그 출력 문자열입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 디버거 출력 이벤트를 처리합니다.  
  
## 참고 항목  
 [IRemoteDebugApplicationEvents 인터페이스](../../winscript/reference/iremotedebugapplicationevents-interface.md)