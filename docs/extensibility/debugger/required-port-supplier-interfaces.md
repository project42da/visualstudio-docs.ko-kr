---
title: 필수 포트 공급자 인터페이스가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e34627effce5e2f0d1401da683536548a32d3f6e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="required-port-supplier-interfaces"></a>필요한 포트 공급자 인터페이스
포트 공급자를 구현 해야 합니다는 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스.[ IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 포트 공급자를 제공 하므로 포트, 해당 구현도 해야 합니다. 따라서 다음 인터페이스를 구현 해야 합니다.  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     포트를 설명 하 고 포트에서 실행 중인 모든 프로세스를 열거할 수 있습니다.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     시작 하 고 포트에서 프로세스 종료를 제공 합니다.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     에 프로그램 노드 생성 및 소멸 알립니다이 포트의이 컨텍스트 내에서 실행 되는 프로그램에 대 한 메커니즘을 제공 합니다. 자세한 내용은 참조 [프로그램 노드](../../extensibility/debugger/program-nodes.md)합니다.  
  
-   `IConnectionPointContainer`  
  
     에 대 한 연결 지점을 제공 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)합니다.  
  
## <a name="port-supplier-operation"></a>포트 공급자 작업  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) 싱크 프로세스 한 알림을 수신 하 고 프로그램 생성 되 고 포트에서 제거 합니다. 포트를 보내는 데 필요한 [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) 프로세스가 만들어질 때 및 [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) 포트에서 프로세스는 소멸 시기입니다. 포트를 보내는 데 필요한도 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 프로그램을 만들 때 및 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 프로그램 포트에서 실행 되는 프로세스에서 소멸 됩니다 때.  
  
 포트는 일반적으로 보내고 프로그램 생성 및 소멸 이벤트에 대 한 응답에서에서 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 및 [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 메서드를 각각.  
  
 포트를 시작 하 고 실제 프로세스와 논리 프로그램 둘 다를 종료할 수, 때문에 이러한 인터페이스 디버그 엔진에서 구현 합니다.  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     실제 프로세스에 설명 합니다. 최소한 다음 메서드를 구현 해야 합니다.  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     SDM 연결 및 자체 프로세스에서 분리 하는 방법을 제공 합니다.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     논리 프로그램에 설명합니다. 최소한 다음 메서드를 구현 해야 합니다.  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     이 프로그램에 연결할 SDM 방법을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)