---
title: "IDebugProgramDestroyEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramDestroyEvent2"
helpviewer_keywords: 
  - "IDebugProgramDestroyEvent2"
ms.assetid: ddf127ca-c4a5-4071-90ca-68faf2f57dbd
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugProgramDestroyEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\)는 프로그램 실행이 완료 된 때 세션 디버그 매니저 \(SDM\) 보내집니다.  
  
## 구문  
  
```  
IDebugProgramDestroyEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스에는 프로그램 종료 되었습니다 하 고 디버깅 하는 데 사용할 수 없습니다 보고서는 DE 또는 사용자 지정 포트 공급자 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 또는 사용자 지정 포트 공급자 만들고이 이벤트 개체는 프로그램의 종료를 보고 보냅니다.  DE의 사용 하 여이 이벤트를 보냅니다에서 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  이 이벤트를 사용 하는 사용자 지정 포트 공급자 보냅니다 있는 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgramDestroyEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetExitCode](../../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md)|프로그램의 종료 코드를 가져옵니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)