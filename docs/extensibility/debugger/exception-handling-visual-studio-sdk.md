---
title: "예외 처리 (Visual Studio SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 88a862c26dad97eecdb5f372f41a76d7886f32be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="exception-handling-visual-studio-sdk"></a>예외 처리 (Visual Studio SDK)
다음 예외가 throw 되 면 발생 하는 프로세스에 설명 합니다.  
  
## <a name="exception-handling-process"></a>예외 처리 프로세스  
  
1.  먼저 예외가 있지만 디버그 엔진 (DE) 전송 전에 예외 처리기 디버깅 중인 프로그램에 의해 처리 되는 [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) stopping 이벤트로 세션 디버그 관리자 (SDM)에 있습니다. `IDebugExceptionEvent2` 첫째 예외 알림을 중지 하려면 사용자에 게 (디버그 패키지의 예외 대화 상자에 지정 됨) 예외에 대 한 설정을 지정 하는 경우에 전송 됩니다.  
  
2.  SDM 호출 [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) 예외의 속성을 가져오려고 합니다.  
  
3.  패키지에서 호출 하 여 디버그 [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 어떤 옵션을 사용자에 게 표시를 확인 하려면.  
  
4.  디버그 패키지가 첫 번째 예외 대화 상자를 열어 예외를 처리 하는 방법을 사용자에 게 요청 합니다.  
  
5.  사용자가 계속을 선택 하는 경우는 SDM 호출 [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)합니다.  
  
    -   메서드가 S_OK를 반환 하는 경우 호출 [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)합니다.  
  
         또는  
  
         메서드가 프로그램 S_FALSE를 반환 하는 경우 디버깅 중인 예외를 처리할 수 있는 두 번째 기회가 제공 됩니다.  
  
6.  디버깅 중인 프로그램의 두 번째 예외에 대 한 처리기가 있으면는 DE 보냅니다는 `IDebugExceptionEvent2` 으로 SDM에 **EVENT_SYNC_STOP**합니다.  
  
7.  디버그 패키지가 첫 번째 예외 대화 상자를 열어 예외를 처리 하는 방법을 사용자에 게 요청 합니다.  
  
8.  패키지에서 호출 하 여 디버그 [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 어떤 옵션을 사용자에 게 표시를 확인 하려면.  
  
9. 디버그 패키지가 두 번째 예외 대화 상자를 열어 예외를 처리 하는 방법을 사용자에 게 요청 합니다.  
  
10. 메서드가 S_OK를 반환 하는 경우 호출 `IDebugExceptionEvent2::PassToDebuggee`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)