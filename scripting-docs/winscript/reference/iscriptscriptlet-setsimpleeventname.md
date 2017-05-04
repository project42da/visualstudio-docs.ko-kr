---
title: "IScriptScriptlet::SetSimpleEventName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptScriptlet.SetSimpleEventName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptScriptlet::SetSimpleEventName"
ms.assetid: 7de9132e-635f-45df-9c92-83a24242b477
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IScriptScriptlet::SetSimpleEventName
스크립트릿으로 연결 된 간단한 이벤트 이름을 설정 합니다.  이 공백은 포함 하지 않는 단일 word 이름입니다.  
  
## 구문  
  
```  
HRESULT SetSimpleEventName(  
   LPCOLESTR          psz  
);  
```  
  
#### 매개 변수  
 `psz`  
 \[in\] 연결 된 간단한 이벤트 이름이 들어 있는 버퍼를 `IScriptScriptlet` 개체입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptScriptlet 인터페이스](../../winscript/reference/iscriptscriptlet-interface.md)