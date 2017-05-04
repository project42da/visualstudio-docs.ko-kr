---
title: "IDebugApplication::HandleBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.HandleBreakPoint
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::HandleBreakPoint"
ms.assetid: 97219bdf-a39a-4e69-81ac-4ca2afe77ce5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::HandleBreakPoint
현재 스레드를 차단 하 고 IDE 디버거에서 중단점에 대 한 알림을 보냅니다.  
  
## 구문  
  
```  
HRESULT HandleBreakPoint(  
   BREAKREASON         br,  
   BREAKRESUMEACTION*  pbra  
);  
```  
  
#### 매개 변수  
 `br`  
 \[in\] 중단 이유  
  
 `pbra`  
 \[out\] 디버거에서 응용 프로그램을 다시 시작할 때 수행할 동작입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 언어 엔진 중단점이 적중 스레드 컨텍스트에서이 메서드를 호출 합니다.  이 메서드는 현재 스레드를 차단 하 고 IDE 디버거 중단점 알림을 보냅니다.  디버거에서 응용 프로그램을 다시 시작 될 때의 `pbra` 매개 변수 동작을 지정 합니다.  
  
> [!NOTE]
>  언어 엔진 등 열거 스택 프레임 또는 중단점 중 식 평가 작업을 수행 하는 스레드가 호출할 수 있습니다.  
  
 이 메서드로 인해 `IApplicationDebugger::onHandleBreakPoint` 호출할 수 있습니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onHandleBreakPoint](../../winscript/reference/iapplicationdebugger-onhandlebreakpoint.md)   
 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)