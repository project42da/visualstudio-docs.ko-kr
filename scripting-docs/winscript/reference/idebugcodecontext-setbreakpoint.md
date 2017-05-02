---
title: "IDebugCodeContext::SetBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugCodeContext.SetBreakPoint
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugCodeContext::SetBreakPoint"
ms.assetid: ecd42eae-66fa-40d3-9e47-08b826784108
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugCodeContext::SetBreakPoint
설정 하거나 여기서 코드에서 중단점을 지웁니다.  
  
## 구문  
  
```  
HRESULT SetBreakPoint(  
   BREAKPOINT_STATE  bps  
);  
```  
  
#### 매개 변수  
 `bps`  
 \[in\] 중단점 상태가이 코드의 컨텍스트를 지정합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드를 설정 하거나 여기서 코드에서 중단점을 지웁니다.  
  
## 참고 항목  
 [IDebugCodeContext 인터페이스](../../winscript/reference/idebugcodecontext-interface.md)   
 [BREAKPOINT\_STATE 열거형](../../winscript/reference/breakpoint-state-enumeration.md)