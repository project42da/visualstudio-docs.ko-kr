---
title: "IDebugHelper::CreateSimpleConnectionPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugHelper.CreateSimpleConnectionPoint
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugHelper::CreateSimpleConnectionPoint"
ms.assetid: 5e4798ce-6f9f-4184-9853-67bf8c8524ab
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugHelper::CreateSimpleConnectionPoint
반환 이벤트 인터페이스를 래핑하는 주어진 `IDispatch` 개체입니다.  
  
## 구문  
  
```  
HRESULT CreateSimpleConnectionPoint(  
   IDispatch*                pdisp   
   ISimpleConnectionPoint**  ppscp  
);  
```  
  
#### 매개 변수  
 `pdisp`  
 \[in\] `IDispatch` 개체를 래핑합니다.  
  
 `ppscp`  
 \[out\] 배치 하는 이벤트 인터페이스 `pdisp`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 반환 이벤트 인터페이스를 래핑하는 주어진 `IDispatch` \(참조 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)\).  
  
## 참고 항목  
 [IDebugHelper 인터페이스](../../winscript/reference/idebughelper-interface.md)   
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)