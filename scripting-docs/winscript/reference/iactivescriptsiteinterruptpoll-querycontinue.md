---
title: "IActiveScriptSiteInterruptPoll::QueryContinue | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteInterruptPoll.QueryContinue
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteInterruptPoll::QueryContinue"
ms.assetid: 41ac3807-f8b4-4a0e-bcc6-556bc89f3904
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteInterruptPoll::QueryContinue
스크립트 종료 됨을 지정 하는 데가 있습니다.  
  
## 구문  
  
```  
HRESULT QueryContinue();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|호출이 성공 하 고 호스트는 스크립트를 계속 실행할 수 있습니다.|  
|`S_FALSE`|호출 성공 및 종료 스크립트 호스트 요청 합니다.|  
  
## 설명  
 하지 않으면 스크립트 호스트를 종료 해야의 반환 값은 `QueryContinue` 메서드입니다 `S_OK`.  반환 값이 `S_FALSE` 스크립트 종료 호스트 명시적으로 요청을 나타냅니다.  
  
 다중 스레드 호스트에서 사용할 수 있는 `IActiveScript::InterruptScriptThread` 메서드는 스크립트를 종료 합니다.  
  
## 참고 항목  
 [IActiveScriptSiteInterruptPoll 인터페이스](../../winscript/reference/iactivescriptsiteinterruptpoll-interface.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)