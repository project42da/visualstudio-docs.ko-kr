---
title: "IBindEventHandler::BindHandler | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IBindEventHandler.BindHandler
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IBindEventHandler::BindHandler"
ms.assetid: 87909828-2224-4bb1-a6c9-dfe715ac4c9b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IBindEventHandler::BindHandler
이벤트 개체에 바인딩합니다.  
  
## 구문  
  
```  
HRESULT BindHandler(  
   LPCOLESTR   pstrEvent,  
   IDispatch*  pdisp  
);  
```  
  
#### 매개 변수  
 `pstrEvent`  
 \[in\] 처리할 이벤트를 지정 합니다.  
  
 `pdisp`  
 \[in\] 이벤트를 처리 하는 개체를 지정 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 이벤트 개체에 바인딩합니다.  
  
## 참고 항목  
 [IBindEventHandler 인터페이스](../../winscript/reference/ibindeventhandler-interface.md)