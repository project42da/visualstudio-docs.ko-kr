---
title: "IActiveScript::SetScriptState | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.SetScriptState
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_SetScriptState"
ms.assetid: f2b2700c-0c8d-40db-ad84-dc751c5d9bc2
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScript::SetScriptState
스크립팅 엔진이 지정 된 상태로 전환합니다.  자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스.  
  
## 구문  
  
```  
HRESULT SetScriptState(  
    SCRIPTSTATE ss  // identifier of new state  
);  
```  
  
#### 매개 변수  
 `ss`  
 \[in\] 스크립팅 엔진이 지정 된 상태로 설정합니다.  정의 된 값 중 하나일 수는 [SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md) 열거형입니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_FAIL`|스크립팅 엔진이 초기화 상태로 전환을 지원 하지 않습니다.  호스트 해야이 스크립팅 엔진 및 만들기, 초기화, 버리고 동일한 효과 얻기 위해 새 스크립트 엔진을 로드 합니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\) 및 따라서 실패 합니다.|  
|`OLESCRIPT_S_PENDING`|메서드는 성공적으로 큐에 대기 된 상태는 변경 되지 않습니다.  면 상태 변경, 사이트 호출 됩니다 다시 통해는 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.|  
|`S_FALSE`|메서드가 성공 했지만 스크립트는 이미 주어진된 상태에서 했습니다.|  
  
## 설명  
 스크립팅 엔진 상태에 대 한 자세한 정보는 스크립트 엔진 상태 절을 참조 하십시오. [Windows 스크립트 엔진](../../winscript/windows-script-engines.md) .  
  
## 참고 항목  
 [IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)   
 [IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)   
 [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)   
 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)