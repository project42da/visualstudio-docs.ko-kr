---
title: "IActiveScriptSite::OnEnterScript | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.OnEnterScript
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_OnEnterScript"
ms.assetid: 1ed9178c-fe80-41c4-b74d-23b85f9cddbf
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::OnEnterScript
스크립팅 엔진이 스크립트 코드를 실행을 시작 했음을 호스트에 게 알립니다.  
  
## 구문  
  
```  
HRESULT OnEnterScript(void);  
```  
  
## 반환 값  
 성공하면 `S_OK`를 반환합니다.  
  
## 설명  
 스크립팅 엔진이이 메서드의 모든 항목 또는 재진입이 스크립팅 엔진에 호출 해야 합니다.  예를 들어, 스크립트 개체는 호출 하 고 스크립팅 엔진에서 처리 하는 이벤트를 발생 하는 경우 스크립팅 엔진 호출 해야 `IActiveScriptSite::OnEnterScript` 전에 이벤트를 실행 하 고 호출 해야는 [IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md) 메서드는 이벤트를 실행 후 이벤트를 발생 시킨 개체를 반환 하기 전에.  이 메서드를 호출 하는 중첩 될 수 있습니다.  이 메서드를 호출할 때마다 해당 호출을 필요 `IActiveScriptSite::OnLeaveScript`.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)