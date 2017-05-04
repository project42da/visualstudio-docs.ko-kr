---
title: "IActiveScriptSite::OnLeaveScript | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.OnLeaveScript
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_OnLeaveScript"
ms.assetid: 79af0e22-fbe3-4fae-8a5f-7af8b857678d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::OnLeaveScript
스크립팅 엔진이 스크립트 코드 실행에서 반환 되었음을 호스트에 게 알립니다.  
  
## 구문  
  
```  
HRESULT OnLeaveScript(void);  
```  
  
## 반환 값  
 성공하면 `S_OK`를 반환합니다.  
  
## 설명  
 스크립트 엔진 스크립팅 엔진이 입력 호출 응용 프로그램에 제어를 반환 하기 전에이 메서드를 호출 해야 합니다.  예를 들어, 스크립트 개체는 호출 하 고 스크립팅 엔진에서 처리 하는 이벤트를 발생 하는 경우 스크립팅 엔진 호출 해야는 [IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md) 메서드는 이벤트를 실행 하기 전에 호출 해야 하 고 `IActiveScriptSite::OnLeaveScript` 이벤트를 발생 시킨 개체를 반환 하기 전에 이벤트를 실행 한 후.  이 메서드를 호출 하는 중첩 될 수 있습니다.  모든 호출에 `IActiveScriptSite::OnEnterScript` 해당이 메서드를 호출 해야 합니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)