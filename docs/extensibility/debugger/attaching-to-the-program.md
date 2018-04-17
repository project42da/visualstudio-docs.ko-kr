---
title: 프로그램에 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: 9a3f5b83-60b5-4ef0-91fe-a432105bd066
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0a4c9719f6258f3bbb5cc8323693001c7f1a9d47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="attaching-to-the-program"></a>프로그램에 연결
적절 한 포트와 프로그램을 등록 하면 디버깅할 프로그램에 디버거를 연결 해야 합니다.  
  
## <a name="choosing-how-to-attach"></a>연결 하는 방법 선택  
 세션 디버그 관리자 (SDM)를 디버깅 중인 프로그램에 연결 하려고 하는 세 가지가 있습니다.  
  
1.  통해 디버그 엔진에 의해 시작 되는 프로그램에 대해는 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 메서드 (예: 해석 된 언어의 일반)은 SDM 가져옵니다는 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 에서 인터페이스 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 에 붙는 프로그램과 연결 된 개체입니다. SDM 얻을 수 있는 경우는 `IDebugProgramNodeAttach2` 인터페이스는 SDM 다음 호출에서 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드. `IDebugProgramNodeAttach2::OnAttach` 메서드 반환 `S_OK` 를 프로그램에 연결 하지 않은 나타내고 프로그램에 연결 하도록 다른 시도 만들 수 있습니다.  
  
2.  SDM 얻을 수 있는 경우는 [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md) SDM 호출에 연결 되는 프로그램에서 인터페이스는 [연결](../../extensibility/debugger/reference/idebugprogramex2-attach.md) 메서드. 이 방법은 포트 공급자가 원격으로 실행 하는 프로그램에 일반적입니다.  
  
3.  프로그램을 통해 연결할 수 없습니다. 경우는 `IDebugProgramNodeAttach2::OnAttach` 또는 `IDebugProgramEx2::Attach` 메서드는 SDM 디버그 엔진 (아직 로드) 하는 경우 호출 하 여 로드는 `CoCreateInstance` 함수 및 호출은 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드. 이 방법은 포트 공급자에 의해 로컬로 시작 프로그램에 일반적입니다.  
  
     호출 하는 사용자 지정 포트 공급자에 대 한도 가능는 `IDebugEngine2::Attach` 의 사용자 지정 포트 공급 업체의 구현에서 메서드는 `IDebugProgramEx2::Attach` 메서드. 일반적으로 경우 사용자 지정 포트 공급자 시작 원격 시스템에서 디버그 엔진 합니다.  
  
 첨부 파일 세션 디버그 관리자 (SDM)를 호출 하는 때 달성 되는 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  
  
 프로그램 DE 디버그 해야 하는 응용 프로그램과 동일한 프로세스에서 실행할 경우는 다음과 같은 방법을 구현 해야 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md):  
  
-   [GetHostName](../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md),  
  
-   [GetHostPid](../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)  
  
-   [GetProgramName](../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)  
  
 후의 `IDebugEngine2::Attach` 메서드는, 구현에서 다음 단계는 `IDebugEngine2::Attach` 메서드:  
  
1.  보내기는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 이벤트 개체는 SDM입니다. 자세한 내용은 참조 [이벤트를 보내는](../../extensibility/debugger/sending-events.md)합니다.  
  
2.  호출의 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 에서 메서드는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 에 전달 된 개체는 `IDebugEngine2::Attach` 메서드.  
  
     반환 합니다.는 `GUID` 프로그램을 식별 하는 데 사용 되는 합니다. `GUID` DE, 나타내는 로컬 프로그램 및 그 해야 하면 반환 된 개체에 저장 되어야 합니다는 `IDebugProgram2::GetProgramId` 메서드가 호출 되는 `IDebugProgram2` 인터페이스입니다.  
  
    > [!NOTE]
    >  구현 하는 경우는 `IDebugProgramNodeAttach2` 인터페이스, 프로그램의 `GUID` 에 전달 되는 `IDebugProgramNodeAttach2::OnAttach` 메서드. 이 `GUID` 는 프로그램에 대 한 사용 `GUID` 에서 반환 되는 `IDebugProgram2::GetProgramId` 메서드.  
  
3.  보내기는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 은 SDM 알리는 이벤트 개체는 로컬 `IDebugProgram2` 는 DE에 프로그램을 나타내는 개체를 만든 합니다. 자세한 내용은 참조 [이벤트를 보내는](../../extensibility/debugger/sending-events.md)합니다.  
  
    > [!NOTE]
    >  이 다르면 `IDebugProgram2` 에 전달 된 개체는 `IDebugEngine2::Attach` 메서드. 이전에 전달 된 `IDebugProgram2` 개체를 포트에만 인식 하며 별도 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 기반 첨부 파일](../../extensibility/debugger/launch-based-attachment.md)   
 [이벤트 전송](../../extensibility/debugger/sending-events.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)   
 [연결](../../extensibility/debugger/reference/idebugprogramex2-attach.md)   
 [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md)