---
title: "IActiveScript::InterruptScriptThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.InterruptScriptThread
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_InterruptScriptThread"
ms.assetid: 2304d035-6d39-4811-acd3-8a9640fdbef6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::InterruptScriptThread
실행 중인 스크립트 스레드 \(이벤트 싱크, 즉시 실행, 또는 매크로 호출\)의 실행을 중단합니다.  \(예를 들어, 무한 루프에\) 걸린 스크립트를 종료 하려면이 메서드를 사용할 수 있습니다.  이 비 기본 스레드에서 자료 설명선 호스트 개체 또는 결과 없이 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 메서드.  
  
## 구문  
  
```  
HRESULT InterruptScriptThread(  
    SCRIPTTHREADID   stidThread,  // identifier of thread  
    const EXCEPINFO *pexcepinfo,  // receives error information  
    DWORD dwFlags  
);  
```  
  
#### 매개 변수  
 `stidThread`  
 \[in\] 다음 별도 스레드 식별자 값 중 하나 또는 인터럽트 스레드 식별자:  
  
|값|의미|  
|-------|--------|  
|SCRIPTTHREADID\_ALL|모든 스레드입니다.  인터럽트 현재 진행 중인 모든 스크립트 메서드에 적용 됩니다.  스크립트 연결이 호출자에 게 요청 하지 않으면 다음 스크립트 이벤트 스크립트 코드를 호출 하 여 다시 실행할 수 있습니다는 [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) SCRIPTSTATE\_DISCONNECTED 또는 SCRIPTSTATE\_INITIALIZED 플래그를 설정한 방법.|  
|SCRIPTTHREADID\_BASE|기본 스레드. 즉, 스크립트에서 엔진 스레드를 인스턴스화 되었습니다.|  
|SCRIPTTHREADID\_CURRENT|현재 실행 중인 스레드입니다.|  
  
 `pexcepinfo`  
 \[in\] 주소는 `EXCEPINFO` 중단 된 스크립트를 보고 해야 하는 오류 정보를 포함 하는 구조입니다.  
  
 `dwFlags`  
 \[in\] 중단에 관련 된 옵션 플래그입니다.  다음 중 한 가지 값을 지정할 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|SCRIPTINTERRUPT\_DEBUG|지원 되는 경우 스크립팅 엔진의 디버거가 현재 스크립트 실행 위치를 입력 합니다.|  
|SCRIPTINTERRUPT\_RAISEEXCEPTION|스크립트 엔진의 언어에서 지 원하는 경우 스크립트를 예외를 처리할 수 있습니다.  그렇지 않으면 스크립트 메서드를 중단 하 고 오류 코드를 호출자에 게 반환 됩니다. 예: 이벤트 소스 또는 매크로 호출자.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)