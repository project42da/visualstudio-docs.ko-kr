---
title: "프로그램 종료 | Microsoft Docs"
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
  - "프로그램 종료 이벤트"
  - "디버깅 [디버깅 SDK], 프로그램 종료"
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로그램 종료
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음은 스레드를 단일 프로그램의 종료에 대 한 설명입니다.  
  
## 종료 프로세스  
  
1.  DE 센드는  [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) 에 잘못 된  [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  DE 센드는  [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 에 잘못 된  [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 IDE 디자인 모드로 이동합니다.  디버그 엔진 또는 런타임 환경 호출  [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 의 포트에서 프로그램을 제거 합니다.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)