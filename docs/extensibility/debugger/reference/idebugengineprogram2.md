---
title: "IDebugEngineProgram2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngineProgram2"
helpviewer_keywords: 
  - "IDebugEngineProgram2 인터페이스"
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugEngineProgram2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 다중 스레드 디버깅 지원을 제공합니다.  
  
## 구문  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 동시 다중 스레드 디버깅을 지원 하기 위해이 인터페이스를 구현 합니다.  이 인터페이스를 구현 하는 동일한 개체에서 구현 되는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 `IDebugProgram2` 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugEngineProgram2`.  
  
|메서드|설명|  
|---------|--------|  
|[중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|이 프로그램에서 실행 중인 모든 스레드를 중지 합니다.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|실행 또는 실행을 위해 감시 중지에 대 한 감시는 주어진된 스레드에서 발생 합니다.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|허용 하거나 허용 하지 않습니다 식 계산 프로그램이 중지 되는 경우에 해당된 스레드에서 발생 합니다.|  
  
## 설명  
 Visual Studio 호출에 응답 하 여이 인터페이스는 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트와 프로그램의 "감시에 대 한 스레드 단계" 및 "에 대 한 식을 계산에서 스레드 보기" 상태를 설정 합니다.  [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)프로그램이 중지 될 때마다 호출 됩니다. 이 메서드는 프로그램 모든 스레드를 종료할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)