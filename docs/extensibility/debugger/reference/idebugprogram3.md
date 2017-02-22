---
title: "IDebugProgram3 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProgram3 인터페이스"
ms.assetid: 4301ba23-c00c-4ce5-8b1e-3f27da312034
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스에서 실행 되 고 확장 프로그램이이 인터페이스를 나타내는 [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md) 스레드 정보를 제공 합니다.  
  
## 구문  
  
```  
IDebugProgram3 : IDebugProgram3  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 및 사용자 지정 포트 공급자는 프로그램 프로세스에서를 나타내는 데이 인터페이스를 구현 합니다.  또한 세션 디버그 매니저 \(SDM\) 정보를 제공할 수이 인터페이스는 구현 [연결](../../../extensibility/debugger/reference/idebugprogram2-attach.md).  
  
## 호출자에 대 한 참고 사항  
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트가 새 프로그램에 대 한이 인터페이스를 반환 합니다.  이 인터페이스는 여러 인터페이스에서 많은 방법에 대 한 매개 변수로 사용 됩니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgram3`.  
  
|메서드|설명|  
|---------|--------|  
|[ExecuteOnThread](../../../extensibility/debugger/reference/idebugprogram3-executeonthread.md)|프로그램을 실행합니다.  스레드는 스레드를 실행 하는 동안 사용자를 보고 있는 디버거 정보를 제공 합니다 반환 됩니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 설명  
 프로그램 프로세스 하나 이상의 프로그램을 구성 하는 동안은 특정 런타임 아키텍처에서 실행 되는 스레드 컨테이너입니다.  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Attach\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)