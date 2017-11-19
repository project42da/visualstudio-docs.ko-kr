---
title: "프로그램에 직접 연결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, attaching to programs
ms.assetid: ad2b7db8-821c-440c-ba07-c55c6a395e0f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8818a57d50595b3c40fa45875a1dfe23d34fb369
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="attaching-directly-to-a-program"></a>프로그램에 직접 연결
일반적으로 이미 실행 중인 프로세스에서 프로그램을 디버깅 하려는 사용자는이 프로세스를 따릅니다.  
  
1.  IDE에서 선택 된 **프로세스 디버그** 명령을 **도구** 메뉴.  
  
     **프로세스** 대화 상자가 나타납니다.  
  
2.  프로세스를 선택 하 고 클릭 하 고 **연결** 단추입니다.  
  
     **프로세스에 연결** 대화 상자가 나타나면는 컴퓨터에 설치 되어 있는 모든 디버그 엔진 (DEs)를 나열 합니다.  
  
3.  선택한 프로세스를 디버깅 하 고 클릭 하는 데 DEs 지정 **확인**합니다.  
  
 디버그 패키지가 디버그 세션을 시작 하 고에 DEs 목록이 전달 합니다. 디버그 세션에이 목록의 선택 된 프로세스에는 콜백 함수를 전달 하 고 그런 다음 해당 실행 중인 프로그램을 열거 하는 프로세스를 묻습니다.  
  
 프로그래밍 방식으로 사용자 요청에 대 한 응답, 디버그 패키지가 세션 디버그 관리자 (SDM) 인스턴스화 및 선택한 DEs 목록을 전달 합니다. 목록과 함께 디버그 패키지가 전달은 SDM는 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 인터페이스입니다. 디버그 패키지가 DEs 목록은 선택한 프로세스를 호출 하 여 전달 [IDebugProcess2::Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)합니다. 다음은 SDM를 호출 [IDebugProcess2::EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 열거 프로세스에서 실행 중인 프로그램에 대 한 포트입니다.  
  
 이 시점부터 각 디버그 엔진은 단계에서 설명한 대로 정확 하 게 프로그램에 연결 된 [연결 후 정도 시작](../../extensibility/debugger/attaching-after-a-launch.md), 두 가지 예외가 있습니다.  
  
 효율성을 높이기 위해 DEs은 SDM와 주소 공간을 공유 하기 위해 구현 되는 각 DE는 일련의 프로그램을 연결할 수 있도록 그룹화 됩니다. 이 경우 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) 호출 [IDebugEngine2::Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) 연결할 프로그램 배열을 전달 합니다.  
  
 두 번째 예외는 이미 실행 중인 프로그램에 연결 하는 DE 전송한 시작 이벤트가 포함 되어 있는지 일반적으로 항목 시점 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 후 시작 이벤트를 전송합니다.](../../extensibility/debugger/sending-startup-events-after-a-launch.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)