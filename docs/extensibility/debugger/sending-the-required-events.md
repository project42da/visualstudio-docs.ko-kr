---
title: "필요한 이벤트 보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 필요 이벤트"
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 필요한 이벤트 보내기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

필요한 이벤트를 보내기 위해이 절차를 사용 합니다.  
  
## 필요한 이벤트를 보내는 과정  
 다음 이벤트 만들기 디버그 엔진 \(DE\) 하는 경우이 순서 및 프로그램을 첨부 필수입니다.  
  
1.  보내기는  [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 세션 디버그 매니저 \(SDM\) 프로세스에서 하나 이상의 프로그램을 디버깅 하는 데는 DE 초기화할 때 이벤트 개체입니다.  
  
2.  디버깅할 프로그램에 연결 하면 보내기는  [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 개체는 SDM.  이 이벤트는 중지 이벤트 엔진 설계에 따라 될 수 있습니다.  
  
3.  프로세스가 시작 될 때 프로그램에 연결 된 경우, 전송 된  [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) SDM IDE의 새 스레드를 알릴 수 있는 이벤트 개체입니다.  이 이벤트는 중지 이벤트 엔진 설계에 따라 될 수 있습니다.  
  
4.  보내기는  [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 이벤트 개체 로드 작업이 완료 또는 프로그램에 연결 완료 되 면 디버깅 중인 프로그램 있을 때 SDM.  이 이벤트는 중지 이벤트 여야 합니다.  
  
5.  보내는 응용 프로그램을 디버깅 하려면 시작 하는 경우는  [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 이벤트 개체 코드는 런타임 아키텍처에서 첫 번째 명령 실행 될 경우 SDM.  이 이벤트는 항상 중지 이벤트가입니다.  디버깅 세션에 단계별 실행이 이벤트에서 IDE 중단 됩니다.  
  
> [!NOTE]
>  많은 언어 코드 시작 부분에 전역 이니셜라이저 또는 \(CRT 라이브러리 또는 \_Main\)에서 외부, 미리 컴파일된 함수를 사용합니다.  요소의 초기 입력 지점 하기 전에 이러한 형식의 디버깅 된 프로그램의 언어를 포함, 다음이 코드를 실행 하 고 엔트리 포인트 이벤트를 보낸 경우 때 사용자 진입점, 같은  **주** 또는 `WinMain`에 도달 합니다.  
  
## 참고 항목  
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)