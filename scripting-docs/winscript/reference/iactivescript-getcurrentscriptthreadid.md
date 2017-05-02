---
title: "IActiveScript::GetCurrentScriptThreadID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetCurrentScriptThreadID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetCurrentScriptThreadID"
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::GetCurrentScriptThreadID
현재 실행 중인 스레드는 스크립팅 엔진 정의 식별자를 검색합니다.  식별자의 후속 메서드 호출을 스크립트 스레드 실행 컨트롤 같은 사용할 수 있는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 메서드.  
  
## 구문  
  
```  
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### 매개 변수  
 `pstidThread`  
 \[out\] 현재 스레드와 연관 된 스레드 스크립트 식별자를 받는 변수에의 주소입니다.  이 식별자의 스크립팅 엔진에 남아 있지만 Windows 스레드 식별자 복사본 수 있습니다.  Win32 스레드가 종료 되 면이 식별자 할당 되며 이후에 다른 스레드를 할당할 수 있습니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_POINTER` 잘못 된 포인터를 지정 하는 경우.  
  
## 설명  
 자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)