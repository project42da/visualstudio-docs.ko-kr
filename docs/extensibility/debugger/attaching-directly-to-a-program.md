---
title: "프로그램에 직접 연결 | Microsoft Docs"
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
ms.assetid: ad2b7db8-821c-440c-ba07-c55c6a395e0f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 프로그램에 직접 연결
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램은 일반적으로 실행 되는 프로세스에서 디버깅 하려는 사용자가이 프로세스를 따릅니다.  
  
1.  IDE에서 선택 하는  **프로세스 디버그** 명령에서  **도구** 메뉴입니다.  
  
     **프로세스** 대화 상자가 나타납니다.  
  
2.  프로세스를 선택 하 고 클릭은  **첨부** 단추.  
  
     해당  **프로세스에 연결** 대화 상자가 나타나면 컴퓨터에 설치 되어 있는 모든 디버그 엔진 \(DEs\)을 나열 합니다.  
  
3.  선택한 프로세스 디버깅 누른 다음을 사용 하 여 Des를 지정할  **확인**.  
  
 디버그 패키지 디버그 세션을 시작 하 고 목록에 DEs 전달.  디버그 세션에 콜백 함수는 선택한 프로세스를 함께이 목록에 차례로 전달 하 고 프로세스에서 실행 중인 프로그램을 열거 하 고 묻습니다.  
  
 프로그래밍 방식으로 사용자 요청에 대 한 응답으로 디버그 패키지 세션 디버그 매니저 \(SDM\) 상에 서 목록에 선택한 DEs 전달 합니다.  목록에는 SDM 디버그 패키지 전달 된  [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 인터페이스.  디버그 패키지를 호출 하 여 DEs 목록 선택한 프로세스에 가공 패스  [IDebugProcess2::Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md).  SDM은 다음 호출  [IDebugProcess2::EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 프로세스에서 실행 중인 프로그램을 열거 하는 포트입니다.  
  
 이 지점에서 각 디버그 엔진에서 설명한 대로 정확 하 게 하는 프로그램에 연결 된  [첨부 한 후에 시작](../../extensibility/debugger/attaching-after-a-launch.md), 두 가지 예외가 있습니다.  
  
 효율성을 위해 SDM을 주소 공간을 공유 하는 구현 된 DEs 그룹화 됩니다 각 DE는 일련의 프로그램에 연결할 수 있도록 합니다.  이 경우  [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) 호출  [IDebugEngine2::Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) 를 연결 하는 프로그램의 배열을 전달 합니다.  
  
 이미 실행 중인 프로그램에 연결 하는 DE에서 보낸 시작 이벤트 엔트리 포인트 이벤트 일반적으로 포함 되지 않는 두 번째 예외가 있습니다.  
  
## 참고 항목  
 [시작 된 후 시작 이벤트를 전송합니다.](../../extensibility/debugger/sending-startup-events-after-a-launch.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)