---
title: "연결을 시작한 후 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, attaching to programs
ms.assetid: 5a3600a1-dc20-4e55-b2a4-809736a6ae65
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 890023b8336f130cf3b8cfcfe640da46af9cf0d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="attaching-after-a-launch"></a>연결을 시작한 후
프로그램 시작 되었습니다 후 디버그 세션을 언급된 프로그램 디버그 엔진 (DE) 연결할 수 있습니다.  
  
## <a name="design-decisions"></a>설계 결정 사항  
 통신 공유 되는 주소 공간 내에서 보다 쉽게 이기 때문에 디버그 세션 사이 DE, 또는 DE와 프로그램 간의 통신을 용이 하 게 하려면 더 많은 적합 한지 결정 해야 합니다. 다음 중에서 선택할.  
  
-   디버그 세션 및는 DE 간의 통신을 돕는 것, 디버그 세션 배치는 DE 만듭니다 및 프로그램에 연결할 DE 요청 합니다. 이런 디버그 세션 및 DE 함께 하나의 주소 공간 및 런 타인 환경 및 프로그램의 다른 함께 있습니다.  
  
-   DE와 프로그램 간의 통신을 용이 하 게 하려면 적절 한 경우, 런타임 환경 배치 만듭니다는 DE. 이런 한 주소 공간에서 SDM DE, 런타임 환경 및 프로그램에서 다른 있습니다. 스크립트 언어를 실행 하는 인터프리터도 구현 된 DE의 일반적입니다.  
  
    > [!NOTE]
    >  DE 프로그램에 연결 하는 방법을 구현에 따라 다릅니다. DE와 프로그램 간의 통신은도 구현에 따라 다릅니다.  
  
## <a name="implementation"></a>구현  
 프로그래밍 방식으로 세션 디버그 관리자 (SDM) 먼저 받을 때의 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 호출을 실행 하도록 프로그램을 나타내는 개체는 [연결](../../extensibility/debugger/reference/idebugprogram2-attach.md) 전달 하는 메서드는 [ IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 이후 개체는 SDM에 다시 디버그 이벤트를 전달 하는 데 사용 합니다. `IDebugProgram2::Attach` 메서드를 호출는 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드. SDM 수신 하는 방법에 대 한 자세한 내용은 `IDebugProgram2` 인터페이스를 참조 [포트 알리는](../../extensibility/debugger/notifying-the-port.md)합니다.  
  
 프로그램 DE 디버깅 중인 프로그램, 일반적으로 DE 스크립트를 실행 하는 인터프리터의 일부 이므로와 같은 주소 공간에서를 실행 해야 하는 경우는 `IDebugProgramNodeAttach2::OnAttach` 메서드가 반환 되 `S_FALSE`, 연결 프로세스를 완료 것을 알립니다.  
  
 DE은 SDM의 주소 공간에서 실행 되는 반면에 하는 경우는 `IDebugProgramNodeAttach2::OnAttach` 메서드 반환 `S_OK` 또는 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 인터페이스에 전혀 구현 되지 않음는 [IDebugProgramNode2 ](../../extensibility/debugger/reference/idebugprogramnode2.md) 디버깅 중인 프로그램와 연결 된 개체입니다. 이 경우에 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드는 결국 연결 작업을 완료 하기 위해 호출 됩니다.  
  
 후자의 경우에 호출 해야 합니다는 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 에서 메서드는 `IDebugProgram2` 에 전달 된 개체는 `IDebugEngine2::Attach` 메서드, 저장소는 `GUID` 로컬 프로그램에서 개체를 만들고이 반환 `GUID` 때는 `IDebugProgram2::GetProgramId` 이후에 메서드는이 개체에 있습니다. `GUID` 다양 한 디버그 구성 요소에서 프로그램을 고유 하 게 식별 하는 데 사용 됩니다.  
  
 경우에는 `IDebugProgramNodeAttach2::OnAttach` 반환 메서드 `S_FALSE`, `GUID` 해당 메서드로 전달 되는 프로그램에 사용할 있고 그것이 `IDebugProgramNodeAttach2::OnAttach` 설정 하는 메서드는 `GUID` 로컬 프로그램 개체에 있습니다.  
  
 프로그램 및 모든 시작 이벤트를 보낼 준비가 이제는 DE 연결 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램에 직접 연결](../../extensibility/debugger/attaching-directly-to-a-program.md)   
 [포트에 게 알리는](../../extensibility/debugger/notifying-the-port.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [연결](../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md)