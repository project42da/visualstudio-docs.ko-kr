---
title: "EVENTATTRIBUTES | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EVENTATTRIBUTES"
helpviewer_keywords: 
  - "EVENTATTRIBUTES 열거형"
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# EVENTATTRIBUTES
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이벤트 속성을 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```c#  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## Members  
 EVENT\_ASYNCHRONOUS  
 이벤트가 비동기적 이며 필요한 응답 하는 이벤트를 나타냅니다.  
  
 EVENT\_SYNCHRONOUS  
 이벤트 동기입니다. 회신 방법으로 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT\_STOPPING  
 중지 이벤트 임을 나타냅니다.  과 함께 사용할 수 `EVENT_ASYNCHRONOUS` 또는 `EVENT_SYNCHRONOUS`.  
  
 EVENT\_ASYNC\_STOP  
 비동기 중지 이벤트를 나타냅니다.  현재 이벤트가 없습니다입니다.  이 플래그는 자리 표시자입니다.  
  
 EVENT\_SYNC\_STOP  
 동기화 중지 이벤트를 나타냅니다 \(함께 `EVENT_SYNCHRONOUS` 및 `EVENT_STOPPING`\).  중지 이벤트를 보낼 때이 값은 디버그 엔진 \(DE\) 사용 됩니다.  응답으로 호출 될 [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md), 또는 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT\_IMMEDIATE  
 IDE로 보내는 즉시, 동기적으로 이벤트를 나타냅니다.  이 플래그는 다른 플래그와 함께 `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, 또는 `EVENT_SYNC_STOP` 이벤트 및 응답 메커니즘 \(있는 경우\) 라고는 팩트 유형을 지정 합니다.  
  
 EVENT\_EXPRESSION\_EVALUATION  
 이벤트 식 계산 결과입니다.  
  
## 설명  
 이 값으로 전달 되는 `dwAttrib` 의 매개 변수는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)