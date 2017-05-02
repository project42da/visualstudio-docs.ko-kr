---
title: "IRemoteDebugApplication 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IRemoteDebugApplication 인터페이스"
ms.assetid: 96bf2a3f-049f-46ba-86ad-57fc184343a2
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IRemoteDebugApplication 인터페이스
실행 중인 응용 프로그램을 나타냅니다.  운영 체제 프로세스에는 해당 하지 않아도 됩니다.  일반적으로 디버거에서 디버깅을 위한 응용 프로그램을 대상 으로합니다.  일반적으로 프로세스 디버그 관리자 응용 프로그램 개체를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IRemoteDebugApplication` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IRemoteDebugApplication::ResumeFromBreakPoint](../../winscript/reference/iremotedebugapplication-resumefrombreakpoint.md)|중단점에는 현재 응용 프로그램을 계속 합니다.|  
|[IRemoteDebugApplication::CauseBreak](../../winscript/reference/iremotedebugapplication-causebreak.md)|응용 프로그램에 디버거를 빨리 중단 됩니다.|  
|[IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)|이 응용 프로그램에 디버거를 연결합니다.|  
|[IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md)|현재 디버거는 응용 프로그램에서 연결을 끊습니다.|  
|[IRemoteDebugApplication::GetDebugger](../../winscript/reference/iremotedebugapplication-getdebugger.md)|디버거에서 현재 응용 프로그램에 연결을 반환 합니다.|  
|[IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md)|IDE에서 실행\-out\-of\-process 응용 프로그램 프로세스에서 개체를 만드는 응용 프로그램에 디버거를 수 있습니다.|  
|[IRemoteDebugApplication::QueryAlive](../../winscript/reference/iremotedebugapplication-queryalive.md)|응용 프로그램 응답 인지 여부를 나타냅니다.|  
|[IRemoteDebugApplication::EnumThreads](../../winscript/reference/iremotedebugapplication-enumthreads.md)|응용 프로그램에 연결 하는 모든 스레드를 열거 합니다.|  
|[IRemoteDebugApplication::GetName](../../winscript/reference/iremotedebugapplication-getname.md)|이 응용 프로그램 노드의 이름을 반환합니다.|  
|[IRemoteDebugApplication::GetRootNode](../../winscript/reference/iremotedebugapplication-getrootnode.md)|연결 된 모든 노드를 추가 하는 데 사용 됩니다 응용 프로그램 노드를 반환 합니다.|  
|[IRemoteDebugApplication::EnumGlobalExpressionContexts](../../winscript/reference/iremotedebugapplication-enumglobalexpressioncontexts.md)|이 응용 프로그램에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 열거 합니다.|