---
title: "IActiveScriptSite::OnStateChange | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.OnStateChange
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_OnStateChange"
ms.assetid: 3e9c5cbe-ca8e-426a-84fd-04e9c2daac7e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSite::OnStateChange
스크립팅 엔진 상태가 변경 되었음을 호스트에 게 알립니다.  
  
## 구문  
  
```  
HRESULT OnStateChange(  
    SCRIPTSTATE ssScriptState  // new state of engine  
);  
```  
  
#### 매개 변수  
 `ssScriptState`  
 \[in\] 새 스크립트 상태를 나타내는 값입니다.  참조는 [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) 메서드 상태 설명.  
  
## 반환 값  
 성공하면 `S_OK`를 반환합니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)