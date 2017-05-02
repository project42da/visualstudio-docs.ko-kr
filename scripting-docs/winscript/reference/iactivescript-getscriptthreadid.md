---
title: "IActiveScript::GetScriptThreadID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetScriptThreadID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetScriptThreadID"
ms.assetid: 2595d76e-30b5-429f-88b4-1d026645dd9b
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScript::GetScriptThreadID
주어진된 Win32 스레드와 연관 된 스레드는 스크립팅 엔진 정의 식별자를 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetScriptThreadID(  
    DWORD dwWin32ThreadID,       // Win32 thread identifier.  
    SCRIPTTHREADID *pstidThread  // Receives scripting thread. identifier  
);  
```  
  
#### 매개 변수  
 `dwWin32ThreadID` ,  
 \[in\] 현재 프로세스에서 실행 중인 Win32 스레드의 스레드 식별자입니다.  사용 된 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md) 함수는 현재 실행 중인 스레드의 스레드 식별자를 검색 합니다.  
  
 `pstidThread` ,  
 \[out\] 주어진된 Win32 스레드에 연결 스크립트 스레드 식별자를 받는 변수에의 주소입니다.  이 식별자의 스크립팅 엔진에 남아 있지만 Windows 스레드 식별자 복사본 수 있습니다.  참고 Win32 스레드가 종료 되 면이 식별자 할당 되 고 나중에 다른 스레드가 할당 될 수 있습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\) 및 따라서 실패 합니다.|  
  
## 설명  
 검색된 식별자 후속 메서드 호출을 스크립트 스레드 실행 컨트롤 처럼 사용할 수 있는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 메서드.  
  
 자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 인터페이스.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)