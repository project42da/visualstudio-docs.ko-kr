---
title: "시작을 기반으로 첨부 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 하는 디버그 엔진"
  - "프로그램에 연결 되는 디버그 엔진"
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 시작을 기반으로 첨부 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

첨부 파일 실행을 기반으로 프로그램을 자동으로 수행 됩니다.  SDM에서 프로그램을 호스팅하는 프로세스를 시작할 때 시작을 기반으로 하는 첨부 파일 수동 첨부 방법을 유사한 경로 다음과 같습니다.  에 대 한 내용은  [프로그램에 연결](../../extensibility/debugger/attaching-to-the-program.md).  
  
## 연결 프로세스  
 주된 차이점은 다음 이벤트의 순서는 있는  **첨부** 는 다음과 같이 호출할:  
  
1.  보내기는  **IDebugEngineCreateEvent2** 이벤트 개체는 SDM.  자세한 내용은  [를 보내는 이벤트](../../extensibility/debugger/sending-events.md).  
  
2.  호출 하는 `IDebugProgram2::GetProgramId` 메서드를는  **IDebugProgram2** 인터페이스를 전달 하는  **첨부** 메서드.  
  
3.  보내기는  **IDebugProgramCreateEvent2** 는 SDM을 알릴 수 있는 이벤트 개체는 로컬  **IDebugProgram2** DE에 프로그램을 나타내는 개체 생성.  
  
4.  보내기는  [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 시작 프로세스에 대해 만든 새 스레드는 SDM을 알릴 수 있는 이벤트 개체입니다.  
  
## 참고 항목  
 [필요한 이벤트 보내기](../../extensibility/debugger/sending-the-required-events.md)   
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)