---
title: "SCRIPTTHREADID 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: SCRIPTTHREADID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "SCRIPTTHREADID"
ms.assetid: 1df9940c-ad0c-42d8-96b9-6a6abe2382e6
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# SCRIPTTHREADID 상수
스레드 유형을 지정 하는 데 사용 합니다.  
  
## 구문  
  
```  
typedef DWORD SCRIPTTHREADID;  
```  
  
## 상수  
  
|상수|값|의미|  
|--------|-------|--------|  
|SCRIPTTHREADID\_CURRENT|0xFFFFFFFD|현재 실행 중인 스레드입니다.|  
|SCRIPTTHREADID\_BASE|0xFFFFFFFE|기본 스레드. 즉, 스크립트에서 엔진 스레드를 인스턴스화 되었습니다.|  
|SCRIPTTHREADID\_ALL|0xFFFFFFFF|모든 스레드입니다.|  
  
## 설명  
 The `SCRIPTTHREADID` type is used by `IActiveScript::GetCurrentScriptThreadID`, `IActiveScript::GetScriptThreadID`, `IActiveScript::GetScriptThreadState`, and `IActiveScript::InterruptScriptThread`, but the constants can only be used by `IActiveScript::GetScriptThreadState` and `IActiveScript::InterruptScriptThread`.  
  
## 참고 항목  
 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)   
 [IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)   
 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)