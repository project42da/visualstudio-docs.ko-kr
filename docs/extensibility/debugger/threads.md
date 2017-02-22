---
title: "스레드 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 스레드 수"
  - "스레딩 [디버깅 SDK]"
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 스레드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **스레드에서**:  
  
-   계산의 기본 단위가입니다.  순차적으로 스레드 컨텍스트 내에서 코드 컨텍스트에 옆에 이동 하는 단일 호출 스택, 지침을 실행 합니다.  
  
-   자체와 프로그램이 실행 되 고 명명 된, 일시 중단, 하 수 계속 식별할 수 있습니다.  스레드에 연결 된 스택 프레임도 열거할 수 있습니다 및 일부 조건에서 다른 스택 프레임으로 이동할 수 있습니다.  스택 프레임의 컨텍스트를 지정 된 경우 스레드가 해당 관련된 논리 스레드가 모든 되돌릴 수 있습니다.  스레드 IDE의 스레드 창에 표시 될 수 있는 일시 중단 횟수가 같은 속성이 있습니다.  
  
-   표시 되는 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) 인터페이스는 일반적으로 디버그 엔진 \(DE\) 또는 가상 머신 결과적으로 프로그램을 실행 하 여 만듭니다.  
  
## 참고 항목  
 [Programs](../../extensibility/debugger/programs.md)   
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [디버그 세션 관리자](../../extensibility/debugger/session-debug-manager.md)