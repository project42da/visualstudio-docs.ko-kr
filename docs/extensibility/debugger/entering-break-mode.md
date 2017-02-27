---
title: "중단 모드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단 모드"
  - "디버깅 [디버깅 SDK], 중단 모드"
ms.assetid: e9a8a241-cd21-4d4e-999a-283554c288b1
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 중단 모드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 함수를 한 단계씩 실행 하 고, 커서를 포함 하는 소스 코드의 줄을 실행 또는 중단점까지 실행 후 중단점을 발견 한 경우 발생 하는 프로세스를 설명 합니다.  
  
## 프로세스 모드 중단  
  
1.  디버그 엔진 \(DE\)을 보냅니다  [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md),  [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md), 또는 IDE 중단 모드를 입력 하 게 다른 중지 이벤트입니다.  
  
2.  SDM은 다음과 같은 호출 스택 정보를에서 스레드를 가져옵니다.  
  
    -   [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)  
  
    -   [IEnumDebugFrameInfo2::GetCount](../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)  
  
    -   [IEnumDebugFrameInfo2::Next](../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)  
  
    -   [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 소스 코드 정보를  
  
    -   [IDebugDocumentContext2::GetName](../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md) 파일 이름  
  
    -   [IDebugDocumentContext2::GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) 문을 범위를 가져오려면  
  
    -   [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) 메모리 정보를 가져올 수  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)