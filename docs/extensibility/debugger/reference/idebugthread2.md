---
title: "IDebugThread2 | Microsoft Docs"
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
  - "IDebugThread2"
helpviewer_keywords: 
  - "IDebugThread2 인터페이스"
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugThread2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 프로그램의 실행 스레드를 나타냅니다.  
  
## 구문  
  
```  
IDebugThread2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 실행 한 프로그램의 스레드를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) 나타내는 현재 활성 스레드에서이 인터페이스를 가져올 수 있습니다.  
  
 이 인터페이스는 중단점 요청을 만드는 데도 사용 됩니다 \(참조 하십시오 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)\).  
  
 이 인터페이스에 오류 또는 중단점을 확인할 때 반환 됩니다 \(참조 하십시오 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 및 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)\).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugThread2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|이 스레드에 대 한 스택 프레임의 목록을 검색합니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)|스레드 이름을 가져옵니다.|  
|[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|스레드 이름을 설정합니다.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|스레드가 실행 되 고 있는 프로그램을 가져옵니다.|  
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|다음 문은 지정 된 스택 프레임 및 코드 컨텍스트를 설정할 수 있는지 여부를 결정 합니다.|  
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|다음 문은 지정 된 스택 프레임 및 코드 컨텍스트를 설정합니다.|  
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|시스템 스레드 식별자를 가져옵니다.|  
|[일시 중단](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|스레드를 일시 중단합니다.|  
|[다시 시작](../../../extensibility/debugger/reference/idebugthread2-resume.md)|스레드를 다시 시작 합니다.|  
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|스레드에 대해 설명 하는 속성을 가져옵니다.|  
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|논리적이 실제 스레드와 연관 된 스레드를 가져옵니다.|  
  
## 설명  
 단일 물리적 스레드 여러 개의 프로그램을 두 개 이상 실행 될 수 있기 때문에 `IDebugThread2` 두 개 이상의 프로그램에서 동일한 실제 스레드에서 나타낼 수 있습니다.  
  
 중단점 또는 예외를 발생 하는 경우 이벤트를 호출 하 여 전송 됩니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  이 메서드의 인수 중 하나가 되는 `IDebugThread2` 인터페이스는 현재 스레드를 표시 합니다.  [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)얻을 하는 데 사용 되는 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 는 현재 스택 프레임에 대 한 인터페이스입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)