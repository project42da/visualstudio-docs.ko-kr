---
title: "예외 처리 (Visual Studio SDK) | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 예외 처리"
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 예외 처리 (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 예외가 throw 될 때 발생 하는 프로세스를 설명 합니다.  
  
## 예외 처리 프로세스  
  
1.  예외가 처음 throw 되었지만 디버깅 중인 프로그램에서 예외 처리기에 의해 처리 되는 전에 디버그 엔진 \(DE\)을 보냅니다 경우는  [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) 중지 이벤트와 세션 디버그 매니저 \(SDM\)에 있습니다.  `IDebugExceptionEvent2` 사용자가 플래그를 첫 번째 예외 알림을 통해 \(예외 대화 상자에서 디버그 패키지 지정\) 예외에 대 한 설정을 지정 하는 경우에 보내집니다.  
  
2.  SDM 호출  [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) 예외의 속성을 가져올 수 있습니다.  
  
3.  디버그 패키지 호출이  [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 사용자에 게 옵션을 결정 합니다.  
  
4.  디버그 패키지 묻는 첫 번째 예외 대화 상자를 열어서 해당 예외를 처리 하는 방법입니다.  
  
5.  사용자가 계속 하도록 선택 하는 경우 호출 하는 SDM  [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).  
  
    -   호출 메서드는 S\_OK를 반환 하는 경우  [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).  
  
         또는  
  
         프로그램 S\_FALSE를 반환 하는 경우 디버깅 중인 예외를 처리 하는 두 번째 기회가 주어입니다.  
  
6.  디버깅 중인 프로그램에 대 한 두 번째 예외 처리기가 없는 경우는 DE 보냅니다 있는 `IDebugExceptionEvent2` 로 SDM을  **EVENT\_SYNC\_STOP**.  
  
7.  디버그 패키지 묻는 첫 번째 예외 대화 상자를 열어서 해당 예외를 처리 하는 방법입니다.  
  
8.  디버그 패키지 호출이  [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 사용자에 게 옵션을 결정 합니다.  
  
9. 디버그 패키지 묻는 두 번째 예외 대화 상자를 열어서 해당 예외를 처리 하는 방법입니다.  
  
10. 호출 메서드는 S\_OK를 반환 하는 경우 `IDebugExceptionEvent2::PassToDebuggee`.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)