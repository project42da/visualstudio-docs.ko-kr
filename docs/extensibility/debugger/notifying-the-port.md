---
title: "포트에 게 알리는 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "포트, 알림"
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 포트에 게 알리는
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램을 시작한 후 포트, 다음과 같은 방법으로 알려야 합니다.  
  
1.  새 프로그램 노드 포트를 수신 하면 디버그 세션을 다시 프로그램 작성 이벤트를 보냅니다.  이벤트와 프로그램을 나타내는 인터페이스를 전달 합니다.  
  
2.  디버그 세션 식별자에 첨부할 수 있는 디버그 엔진 \(DE\)의 프로그램을 쿼리 합니다.  
  
3.  디버그 세션 DE은 해당 프로그램에 대 한 허용 가능한 Des의 목록에 있는지 확인 합니다.  원래는 디버그 패키지에 의해 전달 된 솔루션의 현재 프로그램 설정에서이 목록을 디버그 세션을 가져옵니다.  
  
     DE의 허용 목록에 여야 하며 그렇지 않은 DE 프로그램에 첨부 되지 않습니다.  
  
 프로그래밍 방식으로 새 프로그램 노드의 포트를 처음 받을 때 만듭니다는  [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스 프로그램을 나타낼 수 있습니다.  
  
> [!NOTE]
>  이것을 혼동 하지 마십시오의 `IDebugProgram2` 인터페이스는 디버그 엔진 \(DE\) 나중에 생성 합니다.  
  
 보내는 포트는  [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 프로그램 만들기 이벤트를 다시 COM으로 세션 디버그 매니저 \(SDM\) `IConnectionPoint` 인터페이스입니다.  
  
> [!NOTE]
>  이것을 혼동 하지 마십시오의 `IDebugProgramCreateEvent2` 인터페이스를 DE에서 나중에 전송 됩니다.  
  
 포트, 이벤트 인터페이스 자체를 보냅니다에서  [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md),  [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), 및  [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스는 포트, 프로세스 및 프로그램을 각각 나타냅니다.  SDM 호출  [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) 프로그램을 디버깅 하는 DE의 GUID를 가져올 수 있습니다.  GUID에서 원래 얻 었는  [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다.  
  
 SDM은 DE DEs 허용 된 목록에 있는지 확인 합니다 확인 합니다.  원래는 디버그 패키지에 의해 전달 된 솔루션의 현재 프로그램 설정에서이 목록을 SDM을 가져옵니다.  DE의 허용 목록에 여야 하며 그렇지 않은 프로그램에 첨부 되지 않습니다.  
  
 Id는 DE 알게 되 면 해당 SDM 프로그램에 연결할 준비가 되었습니다.  
  
## 참고 항목  
 [프로그램 실행](../../extensibility/debugger/launching-a-program.md)   
 [시작 된 후 연결](../../extensibility/debugger/attaching-after-a-launch.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)