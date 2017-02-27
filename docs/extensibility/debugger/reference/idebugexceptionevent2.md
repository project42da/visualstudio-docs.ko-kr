---
title: "IDebugExceptionEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExceptionEvent2"
helpviewer_keywords: 
  - "IDebugExceptionEvent2 인터페이스"
ms.assetid: 53d32e59-a84b-4710-833e-c5ab08100516
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugExceptionEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 현재 실행 중인 프로그램에서 예외가 throw 되 면이 인터페이스 세션 디버그 매니저 \(SDM\)을 보냅니다.  
  
## 구문  
  
```  
IDebugExceptionEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE는 디버깅 중인 프로그램에서 예외가 발생 했음을 보고할이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들고 예외를 보고 합니다이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 됩니다 있는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugExceptionEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)|이 이벤트가 발생 하는 예외에 대 한 자세한 정보를 가져옵니다.|  
|[GetExceptionDescription](../../../extensibility/debugger/reference/idebugexceptionevent2-getexceptiondescription.md)|이 이벤트가 발생 한 예외에 대 한 사람이 읽을 수 있는 설명을 가져옵니다.|  
|[CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)|디버그 엔진 \(DE\) 실행을 다시 시작 하는 경우에 디버깅 중인 프로그램에이 예외를 전달 하는 옵션을 지원 하는지 여부를 결정 합니다.|  
|[PassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)|예외를 무시 합니다 또는 예외가 실행을 다시 시작 하는 경우 디버깅 중인 프로그램에 전달할지 여부를 지정 합니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 설명  
 검사는 DE 이벤트를 보내기 전에이 예외가 이벤트 첫째 또는 둘째 예외에 대 한 이전 호출에 지정 된 경우 보려면 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md).  첫째 예외에 지정 되어 있는 경우는 `IDebugExceptionEvent2` SDM에 이벤트를 전송 합니다.  그렇지 않은 경우에 DE 응용 프로그램에서 예외를 처리할 수 있습니다.  예외 처리기를 제공 하는 경우 및 예외를 두 번째 기회가 예외에 지정 되어 있는 경우는 `IDebugExceptionEvent2` SDM에 이벤트를 전송 합니다.  그렇지 않으면는 DE 실행 프로그램을 다시 시작 하 고 운영 체제나 런타임 예외를 처리 합니다.  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)