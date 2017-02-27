---
title: "프로그램에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로그램에 연결 되는 디버그 엔진"
ms.assetid: 9a3f5b83-60b5-4ef0-91fe-a432105bd066
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 프로그램에 연결
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

적절 한 포트와 프로그램을 등록 한 후 디버깅 하려는 프로그램에 디버거를 연결 해야 합니다.  
  
## 연결 하는 방법을 선택 합니다.  
 세션 디버그 매니저 \(SDM\) 디버깅 중인 프로그램에 연결 하려고 다음 세 가지가 있습니다.  
  
1.  디버그 엔진을 통해 실행 되는 프로그램에 대 한는 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 는 SDM 메서드 \(일반\)의 해석된 언어를 가져옵니다는 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 에서 인터페이스는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 프로그램에 연결 되 고 연결 된 개체입니다.  SDM을 얻을 수 있으면는 `IDebugProgramNodeAttach2` 인터페이스는 SDM을 다음 호출을 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드.  `IDebugProgramNodeAttach2::OnAttach` 메서드가 반환 `S_OK` 프로그램에 첨부 되지 않았습니다 및 다른 프로그램에 연결 하도록 만들 수 있습니다 나타냅니다.  
  
2.  SDM는 얻을 수 있으면는 [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md) SDM 호출이 연결 되 고 프로그램에서 인터페이스의 [연결](../../extensibility/debugger/reference/idebugprogramex2-attach.md) 메서드.  이 방법은 포트 협력 업체에서 원격으로 실행 한 프로그램에 대 한 일반적인 것입니다.  
  
3.  프로그램을 통해 연결할 수 없습니다 경우는 `IDebugProgramNodeAttach2::OnAttach` 또는 `IDebugProgramEx2::Attach` 메서드는 SDM 로드는 디버그 엔진 \(로드 되지 않은 경우\)를 호출 하 여는 `CoCreateInstance` 함수 및 호출을 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  이 방법은 로컬 포트 공급자가 실행 되는 프로그램에 대 한 일반적입니다.  
  
     수도 있습니다 사용자 지정 포트 공급자를 호출 하 여 `IDebugEngine2::Attach` 메서드를 구현 하는 포트 사용자 지정 공급 업체에에서는 `IDebugProgramEx2::Attach` 메서드.  일반적으로 경우에 사용자 지정 포트 공급자 디버그 엔진 원격 컴퓨터에서 시작합니다.  
  
 첨부 파일이 세션 디버그 매니저 \(SDM\)을 호출 하는 경우 얻을 수 있는 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  
  
 DE를 디버깅 하려면 응용 프로그램으로 동일한 프로세스에서 실행 다음의 다음 메서드를 구현 해야 하는 경우 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md):  
  
-   [GetHostName](../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md),  
  
-   [GetHostPid](../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)  
  
-   [GetProgramName](../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)  
  
 이후에 `IDebugEngine2::Attach` 메서드 호출에서의 구현에서 같이 있는 `IDebugEngine2::Attach` 메서드:  
  
1.  보내기는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 이벤트 개체는 SDM.  자세한 내용은 [이벤트 전송](../../extensibility/debugger/sending-events.md)를 참조하십시오.  
  
2.  호출의 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 방법에의 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 에 전달 된 개체는 `IDebugEngine2::Attach` 메서드.  
  
     이 반환 된 `GUID` 사용 되는 프로그램을 식별 합니다.  `GUID` 나타내는 로컬 프로그램이 DE 하 고 경우 반환 되어야 합니다 개체를 저장 해야 있는 `IDebugProgram2::GetProgramId` 메서드가 호출의 `IDebugProgram2` 인터페이스.  
  
    > [!NOTE]
    >  구현할 클래스는 `IDebugProgramNodeAttach2` 인터페이스, 프로그램의 `GUID` 전달 되는 `IDebugProgramNodeAttach2::OnAttach` 메서드.  이 `GUID` 프로그램에 사용 `GUID` 에서 반환 하는 `IDebugProgram2::GetProgramId` 메서드.  
  
3.  보내기는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 는 SDM을 알릴 수 있는 이벤트 개체는 로컬 `IDebugProgram2` DE에 프로그램을 나타내는 개체 생성.  자세한 내용은 [이벤트 전송](../../extensibility/debugger/sending-events.md)를 참조하십시오.  
  
    > [!NOTE]
    >  이 같은 아닙니다 `IDebugProgram2` 로 전달 된 개체를 `IDebugEngine2::Attach` 메서드.  이전에 전달 된 `IDebugProgram2` 개체의 포트에서 인식 되 고 있는 별도 개체입니다.  
  
## 참고 항목  
 [시작을 기반으로 첨부 파일](../../extensibility/debugger/launch-based-attachment.md)   
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
 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)