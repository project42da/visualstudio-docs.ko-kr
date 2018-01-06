---
title: "첨부 파일 시작 기반 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d05f0b8d8fd0190391da831351b65d873eac4efc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="launch-based-attachment"></a>시작 기반 첨부 파일
프로그램으로 시작 기반 첨부 파일은 자동입니다. 프로그램을 호스트 하는 프로세스는 SDM에 의해 시작 되 면 시작 기반 첨부 파일 수동 첨부 메서드와 비슷한 경로 따릅니다. 자세한 내용은 참조 [은 프로그램에 연결할](../../extensibility/debugger/attaching-to-the-program.md)합니다.  
  
## <a name="the-attaching-process"></a>연결 프로세스  
 주요 차이점은 다음 이벤트의 순서는 **연결** 다음과 같이 호출 합니다.  
  
1.  보내기는 **IDebugEngineCreateEvent2** 이벤트 개체는 SDM입니다. 자세한 내용은 참조 [이벤트를 보내는](../../extensibility/debugger/sending-events.md)합니다.  
  
2.  호출는 `IDebugProgram2::GetProgramId` 에서 메서드는 **IDebugProgram2** 인터페이스에 전달 되는 **연결** 메서드.  
  
3.  보내기는 **IDebugProgramCreateEvent2** 은 SDM 알리는 이벤트 개체는 로컬 **IDebugProgram2** 는 DE에 프로그램을 나타내는 개체를 만든 합니다.  
  
4.  보내기는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 이벤트 개체에 알리는 SDM 새 스레드가 시작 된 프로세스에 대해 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [필요한 이벤트 보내기](../../extensibility/debugger/sending-the-required-events.md)   
 [디버그할 프로그램을 사용하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)