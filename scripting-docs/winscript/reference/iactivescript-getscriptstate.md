---
title: "IActiveScript::GetScriptState | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetScriptState
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetScriptState"
ms.assetid: 59837f7c-755d-45c4-8194-bd57638fe2e1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::GetScriptState
스크립팅 엔진의 현재 상태를 검색합니다.  자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스.  
  
## 구문  
  
```  
HRESULT GetScriptState(  
    SCRIPTSTATE *pss  // address of structure for state information  
);  
```  
  
#### 매개 변수  
 `pss`  
 \[out\] 주소를 정의 하는 값을 받을 변수를 [SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md) 열거형입니다.  값 호출 스레드와 관련 된 스크립팅 엔진의 현재 상태를 나타냅니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_POINTER` 잘못 된 포인터를 지정 하는 경우.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)