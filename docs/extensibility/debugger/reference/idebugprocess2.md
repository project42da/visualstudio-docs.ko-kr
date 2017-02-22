---
title: "IDebugProcess2 | Microsoft Docs"
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
  - "IDebugProcess2"
helpviewer_keywords: 
  - "IDebugProcess2 인터페이스"
ms.assetid: 99f6cd06-4076-45ee-b2ae-fa2ad627fd18
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 포트에서 실행 되는 프로세스를 나타냅니다.  포트를 로컬 포트 다음 인 경우 `IDebugProcess2` 는 일반적으로 실제 프로세스에 로컬 컴퓨터를 나타냅니다.  
  
## 구문  
  
```  
IDebugProcess2 : IUnknown  
```  
  
## 구현자 참고 사항  
 프로그램을 그룹으로 관리 하는 사용자 지정 포트 공급자가이 인터페이스를 구현 합니다.  포트 공급자가이 인터페이스를 구현 해야 합니다.  
  
 통한 프로그램 실행을 지 원하는 경우 디버그 엔진 또한이 인터페이스는 구현 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스 세션 디버그 관리자 \(SDM\)가 주로이 과정에서 식별 된 프로그램 그룹 상호 작용 하기 위해 호출 됩니다.  
  
 호출 [GetProcess](../../../extensibility/debugger/reference/idebugprogram2-getprocess.md) 또는 [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md) 이 인터페이스를 가져올 수 있습니다.  이 인터페이스를 호출 하 여 반환 됩니다 `IDebugEngineLaunch2::LaunchSuspended`.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProcess2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)|프로세스에 대 한 설명을 가져옵니다.|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)|이 프로세스에서 포함 된 프로그램을 열거 합니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)|제목, 이름, 또는 프로세스의 파일 이름을 가져옵니다.|  
|[GetServer](../../../extensibility/debugger/reference/idebugprocess2-getserver.md)|이 프로세스가 실행 되는 컴퓨터의 서버 인스턴스를 가져옵니다.|  
|[종료](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)|프로세스를 종료합니다.|  
|[연결](../../../extensibility/debugger/reference/idebugprocess2-attach.md)|프로세스에 연결합니다.|  
|[CanDetach](../../../extensibility/debugger/reference/idebugprocess2-candetach.md)|SDM을 프로세스를 분리할 수 있습니다 경우 결정 합니다.|  
|[Detach](../../../extensibility/debugger/reference/idebugprocess2-detach.md)|프로세스에서 디버거를 분리 합니다.|  
|[GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)|시스템 프로세스 id를 가져옵니다.|  
|[GetProcessId](../../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)|이 프로세스에 대 한 전역 고유 식별자를 가져옵니다.|  
|[GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)<br /><br /> \[사용\]|프로세스를 디버깅 세션의 이름을 가져옵니다.<br /><br /> \[사용 되지 않습니다.  항상 반환 합니다 `E_NOTIMPL`.\]|  
|[EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)|프로세스에서 실행 중인 스레드를 열거 합니다.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugprocess2-causebreak.md)|다음 프로그램에서이 프로세스가 중지 코드 실행 요청 합니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugprocess2-getport.md)|이 프로세스가 실행 되 고 있는 포트를 가져옵니다.|  
  
## 설명  
 `IDebugProcess2` 하나 이상 들어 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [GetProcess](../../../extensibility/debugger/reference/idebugprogram2-getprocess.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)