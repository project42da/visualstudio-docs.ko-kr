---
title: "프로세스 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 처리"
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로세스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **프로세스**:  
  
-   일련의 프로그램에 대 한 컨테이너가입니다.  컨테이너 스레드 집합에 대 한 Windows 프로세스와 거의 유사 합니다.  
  
-   자체 이름, 식별자 또는 물리적 식별자로 확인할 수 있습니다.  
  
-   실행 중인 모든 프로그램 \(및 해당 스레드\)를 열거할 수 있습니다.  
  
-   에서 실행 되는 포트와 포함 된 시스템을 설명할 수 있습니다.  
  
-   더 많은 프로그램을 작성 하는 프로그램을 종료 하거나 중지 하는 프로그램을 만들 수 있습니다.  
  
-   표시 되는 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) 프로세스가 시작 될 때 만들어지는 인터페이스.  프로세스를 시작할 두 세션 디버그 관리자가 \(SDM\) 또는 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 디버그 패키지를 호출 하 여 프로세스에 디버그 엔진 \(DE\)을 첨부할 수 있습니다 [연결](../../extensibility/debugger/reference/idebugprocess2-attach.md).  이 DE에서 처리할 수 있는 프로세스를 실행 가능한 프로그램을 모두에 연결 되어 있습니다.  예를 들어, DE는 공용 언어 런타임에서 프로세스에 연결 하는 경우 관리 코드를 실행 하는 프로그램에만 연결 합니다.  
  
## 참고 항목  
 [Programs](../../extensibility/debugger/programs.md)   
 [스레드](../../extensibility/debugger/threads.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [패키지를 디버그 합니다.](../../extensibility/debugger/debug-package.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [연결](../../extensibility/debugger/reference/idebugprocess2-attach.md)