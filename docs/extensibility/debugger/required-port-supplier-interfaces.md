---
title: "필요한 포트 공급자 인터페이스 | Microsoft Docs"
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
  - "필요한 인터페이스 포트 공급 업체"
  - "디버깅 [디버깅 SDK] 포트 공급자"
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 필요한 포트 공급자 인터페이스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

포트 공급자 구현 해야는 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스입니다.       [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 포트 포트 공급자가 공급 하기 때문에 그도 구현 해야 합니다.  따라서, 그는 다음 인터페이스를 구현 해야 합니다.  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     포트를 설명 하 고 포트에서 실행 중인 모든 프로세스를 열거할 수 있습니다.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     시작 및 종료 프로세스의 포트를 제공 합니다.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     프로그램 노드 생성 및 소멸을 알리려면이 포트의이 컨텍스트 내에서 실행 되는 프로그램에 대 한 메커니즘을 제공 합니다.  자세한 내용은 [프로그램 노드](../../extensibility/debugger/program-nodes.md)를 참조하십시오.  
  
-   `IConnectionPointContainer`  
  
     에 대 한 연결 지점을 제공 합니다. [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md).  
  
## 포트 공급자 작업  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) 싱크 프로세스 때 알림을 받고 프로그램 생성 되 고 소멸의 포트에 있습니다.  전송 하는 데 필요한 포트를 [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) 프로세스를 만들 때 및 [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) 의 포트에서 프로세스를 파괴 하면.  포트도 보낼 필요 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 프로그램을 만들 때 및 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 프로그램입니다 소멸 시기는 포트에서 실행 되는 프로세스에 있습니다.  
  
 포트 일반적으로 발송 프로그램 만들기 및 소멸 이벤트에 응답 하는 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 및 [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 방법, 각각.  
  
 포트를 시작 하 고 실제 프로세스 및 논리 프로그램을 모두 종료 하기 때문에 이러한 인터페이스 또한 디버그 엔진에 의해 구현 되어야 합니다.  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     실제 프로세스를 설명합니다.  최소한 다음 메서드를 구현 해야 합니다.  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     SDM 연결 하 고 자체를 프로세스에서 분리 하는 방법을 제공 합니다.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     프로그램 논리에 대해 설명 합니다.  최소한 다음 메서드를 구현 해야 합니다.  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     이 프로그램에 연결 하는 SDM의 방법을 제공 합니다.  
  
## 참고 항목  
 [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)