---
title: "IDebugApplication::HandleRuntimeError | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.HandleRuntimeError
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::HandleRuntimeError"
ms.assetid: f8f3bbaf-09e5-4d01-8a35-f380bc7ff8ed
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::HandleRuntimeError
현재 스레드를 차단 하 고 IDE 디버거를 오류에 대 한 알림을 보냅니다.  
  
## 구문  
  
```  
HRESULT HandleRuntimeError(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   IActiveScriptSite*        pScriptSite,  
   BREAKRESUMEACTION*        pbra,  
   ERRORRESUMEACTION*        perra,  
   BOOL*                     pfCallOnScriptError  
);  
```  
  
#### 매개 변수  
 `pErrorDebug`  
 \[in\] 발생 한 오류입니다.  
  
 `pScriptSite`  
 \[in\] 스레드의 스크립트 사이트입니다.  
  
 `pbra`  
 \[out\] 디버거에서 응용 프로그램을 다시 시작할 때 수행할 동작입니다.  
  
 `perra`  
 \[out\] 오류가 있으면 디버거에서 응용 프로그램을 다시 시작할 때 수행할 동작입니다.  
  
 `pfCallOnScriptError`  
 \[out\] 플래그는 `TRUE` 엔진을 호출 해야 하는 경우는 `IActiveScriptSite::OnScriptError` 메서드.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 언어 엔진은 런타임 오류를 발생 시키는 스레드 컨텍스트에서이 메서드를 호출 합니다.  이 메서드는 현재 스레드를 차단 하 고 IDE 디버거를 보낼 수 있는 오류 알림을 보냅니다.  IDE 디버거 응용 프로그램이 다시 시작 될 때 수행할 작업을이 메서드를 반환 합니다.  
  
> [!NOTE]
>  런타임 오류 동안에 언어 엔진 스레드 스택 프레임을 열거 하거나 식을 계산할 때 이러한 작업을 수행 하 여 호출할 수 있습니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IActiveScriptErrorDebug 인터페이스](../../winscript/reference/iactivescripterrordebug-interface.md)   
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION 열거형](../../winscript/reference/errorresumeaction-enumeration.md)