---
title: "IApplicationDebugger::onHandleBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IApplicationDebugger.onHandleBreakPoint
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IApplicationDebugger::onHandleBreakPoint"
ms.assetid: 31adcecd-d6c1-4222-ab2c-32ec2fefb322
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IApplicationDebugger::onHandleBreakPoint
중단점 이벤트를 처리합니다.  
  
## 구문  
  
```  
HRESULT onHandleBreakPoint(  
   IRemoteDebugApplicationThread*  prpt,  
   BREAKREASON                     br,  
   IActiveScriptErrorDebug*        pError  
);  
```  
  
#### 매개 변수  
 `prpt`  
 \[in\] 스레드 중단점 발생 한 위치입니다.  
  
 `br`  
 \[in\] 중단점에 대 한 이유입니다.  
  
 `pError`  
 \[in\] 런타임 오류 정보를 제공 하면 값의 `br` BREAKREASON\_ERROR입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 중단점에 도달 하면이 메서드를 호출 하 고 `IDebugApplication::HandleBreakPoint` 라고 합니다.  
  
 IDE 디버거를 호출할 때까지 응용 프로그램이 일시 중단 된 남아 `IRemoteDebugApplication::ResumeFromBreakPoint`.  
  
## 참고 항목  
 [IApplicationDebugger 인터페이스](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::HandleBreakPoint](../../winscript/reference/idebugapplication-handlebreakpoint.md)   
 [IRemoteDebugApplication::ResumeFromBreakPoint](../../winscript/reference/iremotedebugapplication-resumefrombreakpoint.md)   
 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md)