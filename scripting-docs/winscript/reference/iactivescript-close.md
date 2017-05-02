---
title: "IActiveScript::Close | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.Close
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_Close"
ms.assetid: cc7dd63b-1d7e-410a-857b-09ea3aade275
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScript::Close
스크립팅 엔진에서 현재 로드 된 스크립트를 중단 하 고 해당 상태가 손실가 닫힌된 상태에 따라서 입력 하는 다른 개체에 인터페이스 포인터를 해제 하면 됩니다.  이벤트 싱크, 즉시 실행된 된 스크립트 텍스트 및 이미 진행 중인 매크로 호출 상태 변경 하기 전에 완료 \(사용 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 스크립트 실행 중인 스레드가 취소\).  순환 참조 문제가 발생 하지 않도록 하려면 인터페이스를 릴리스하기 전에 만드는 호스트에서이 메서드를 호출 해야 합니다.  
  
## 구문  
  
```  
HRESULT Close(void);  
```  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|값|의미|  
|-------|--------|  
|`S_OK`|성공|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 이미 닫힌된 상태에서 했습니다\).|  
|`OLESCRIPT_S_PENDING`|메서드는 성공적으로 큐에 대기 된 상태는 변경 되지 않습니다.  상태 변경, 사이트 경우에 호출 되는 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.|  
|`S_FALSE`|메서드가 성공 했지만 스크립트가 이미 닫혔습니다.|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)