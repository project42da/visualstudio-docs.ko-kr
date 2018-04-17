---
title: 필요한 이벤트를 보내는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: deeffb814dacc58b1fb3a3f993203139d9b1a081
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sending-the-required-events"></a>필요한 이벤트 보내기
필요한 이벤트를 보내는 데이 절차를 따르세요.  
  
## <a name="process-for-sending-required-events"></a>필요한 이벤트를 전송에 대 한 프로세스  
 다음 이벤트는 프로그램에 연결 (DE) 엔진 디버그를 만들 때이 순서 대로 필요:  
  
1.  보내기는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 이벤트 개체를 세션 디버그 관리자는 DE 프로세스에서 하나 이상의 프로그램 디버깅을 위해 초기화 될 때 (SDM).  
  
2.  디버깅할 프로그램에 연결 되 면 보내기는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 개체는 SDM입니다. 이 이벤트는 엔진 디자인에 따라 stopping 이벤트를 수 있습니다.  
  
3.  프로세스를 시작할 때 프로그램에 연결 되 면 송신는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 이벤트 개체는 새로운 스레드로 IDE에 알리기 위해 SDM입니다. 이 이벤트는 엔진 디자인에 따라 stopping 이벤트를 수 있습니다.  
  
4.  보내기는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 디버깅 중인 프로그램 완료 로드 또는 때 완료 되는 프로그램에 연결할 때 SDM 이벤트 개체입니다. 이 이벤트는 stopping 이벤트 이어야 합니다.  
  
5.  디버깅할 응용 프로그램을 시작 하는 경우 보내기는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) SDM 런타임 아키텍처에서 코드의 첫 번째 명령 실행 될 때 이벤트 개체입니다. 이 이벤트는 항상 stopping 이벤트. 디버깅 세션에 프로시저를 실행할 때이 이벤트에서 IDE 중지 합니다.  
  
> [!NOTE]
>  여러 언어 코드의 시작 부분에 전역 이니셜라이저 또는 (CRT 라이브러리 _Main)에서 외부 미리 컴파일된 함수를 사용합니다. 디버깅 중인 프로그램의 언어 이러한 유형의 시작 지점 앞 요소 중 하나가 포함 다음이 코드가 실행 되 고 항목 지점 이벤트가 전송 된 때 사용자 항목 포인트 경우와 같은 **주** 또는 `WinMain`, 도달 했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그할 프로그램을 사용하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)