---
title: 포트에 게 알리는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1420ca8768ddf1eaedc0d515810bc88b3491c4db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="notifying-the-port"></a>포트에 게 알리는
프로그램을 시작한 후 포트 알림을 받아야, 다음과 같습니다.  
  
1.  포트를 프로그램에 새 노드를 받으면 프로그램 생성 이벤트를 디버그 세션에 다시 보냅니다. 이벤트에는 저마다 프로그램을 나타내는 인터페이스입니다.  
  
2.  디버그 세션에 연결할 수 있는 디버그 엔진 (DE)의 식별자에 대 한 프로그램을 쿼리 합니다.  
  
3.  디버그 세션에는 DE 해당 프로그램에 대해 DEs 허용 목록에 있는지 확인 합니다. 디버그 세션 원래 디버그 패키지에 의해 전달 되는 솔루션의 활성 프로그램 설정에서이 목록을 가져옵니다.  
  
     DE 허용 목록에 있어야 합니다. 그렇지 않으면 프로그램에는 DE에 연결 되지 않습니다.  
  
 프로그래밍 방식으로 포트를 프로그램에 새 노드를 받으면 먼저 만듭니다는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 프로그램을 나타내는 인터페이스입니다.  
  
> [!NOTE]
>  와 일치 하지 않습니다이 `IDebugProgram2` 디버그 엔진 (DE)에서 나중에 만든 인터페이스입니다.  
  
 포트 보냅니다는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) COM 사용 하 여 세션 디버그 관리자 (SDM)를 다시 생성 이벤트 프로그램 `IConnectionPoint` 인터페이스입니다.  
  
> [!NOTE]
>  와 일치 하지 않습니다이 `IDebugProgramCreateEvent2` 인터페이스는 DE 하 여 나중에 전송 됩니다.  
  
 이벤트 인터페이스 자체와 함께 포트 보냅니다는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), 및 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 포트를 나타내는 인터페이스를 처리 하 고 프로그래밍, 각각. SDM 호출 [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) 프로그램을 디버깅할 수 있는 DE의 GUID를 얻으려고 합니다. GUID를 원래 가져온는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다.  
  
 SDM DEs 허용 목록에는 DE 인지를 확인 합니다. SDM 원래 디버그 패키지에 의해 전달 되는 솔루션의 활성 프로그램 설정에서이 목록을 가져옵니다. DE 허용 목록에 있어야 합니다. 그렇지 않으면 프로그램에 연결 되지 않습니다.  
  
 DE의 id 확인 되 면은 SDM를 프로그램에 연결할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램을 시작](../../extensibility/debugger/launching-a-program.md)   
 [연결을 시작한 후](../../extensibility/debugger/attaching-after-a-launch.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)