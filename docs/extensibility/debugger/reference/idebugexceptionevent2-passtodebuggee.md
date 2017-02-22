---
title: "IDebugExceptionEvent2::PassToDebuggee | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExceptionEvent2::PassToDebuggee"
helpviewer_keywords: 
  - "IDebugExceptionEvent2::PassToDebuggee"
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExceptionEvent2::PassToDebuggee
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

예외를 무시 합니다 또는 예외가 실행을 다시 시작 하는 경우 디버깅 중인 프로그램에 전달할지 여부를 지정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```c#  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### 매개 변수  
 `fPass`  
 \[in\] 0이 아닌 \(`TRUE`\)는 예외 0 또는 실행을 다시 시작 하는 경우 디버깅 중인 프로그램에 전달할지 경우 \(`FALSE`\) 예외를 무시 해야 하는 경우.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출한 코드는 디버깅 중인 프로그램에서 실행 실제로 발생 하지 않습니다.  호출은 다음 코드 실행에 대 한 상태를 설정할 뿐입니다.  예를 들어, 호출 하는 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 메서드를 반환할 수 있다 `S_OK` 에 있는 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md).`dwState` field set to `EXCEPTION_STOP_SECOND_CHANCE`.  
  
 IDE를 나타날 수 있습니다 있는 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) 호출 하 고 이벤트의 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md) 메서드.  디버그 엔진 \(DE\) if 사례를 처리 하는 기본 동작을 가집니다 있는 `PassToDebuggee` 메서드가 호출 됩니다.  
  
## 참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md)