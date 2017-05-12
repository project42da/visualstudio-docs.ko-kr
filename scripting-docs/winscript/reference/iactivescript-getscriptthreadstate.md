---
title: "IActiveScript::GetScriptThreadState | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetScriptThreadState
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetScriptThreadState"
ms.assetid: 7cac94d0-436e-4c29-895b-0c4afa0b3ccc
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScript::GetScriptThreadState
스크립트 스레드의 현재 상태를 검색합니다.  
  
## 구문  
  
```  
HRESULT GetScriptThreadState(  
    SCRIPTTHREADID stidThread,    // identifier of script thread  
    SCRIPTTHREADSTATE *pstsState  // receives state flag  
);  
```  
  
#### 매개 변수  
 `stidThread`  
 \[in\] 상태에 대해 원하는 스레드 식별자 또는 특수 스레드 식별자 다음 중 하나:  
  
|값|의미|  
|-------|--------|  
|SCRIPTTHREADID\_BASE|기본 스레드. 즉, 스크립트에서 엔진 스레드를 인스턴스화 되었습니다.|  
|SCRIPTTHREADID\_CURRENT|현재 실행 중인 스레드입니다.|  
  
 `pstsState`  
 \[out\] 지정 된 스레드의 상태를 받을 변수의 주소입니다.  상태 여 정의 된 명명 된 상수 값 중 하나로 표시 되는 [SCRIPTTHREADSTATE 열거형](../../winscript/reference/scriptthreadstate-enumeration.md) 열거.  이 매개 변수는 현재 스레드 식별 하지 못할 경우 상태는 언제 든 지 변경할 수 있습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
  
## 설명  
 자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)