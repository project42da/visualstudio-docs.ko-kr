---
title: "Programs | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 프로그램"
  - "프로그램을 디버깅"
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# Programs
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **프로그램**:  
  
-   컨테이너의 스레드 세트와 모듈의 집합입니다.  프로그램 없음 단일 비유는 Windows 운영 체제에 있습니다.  
  
     프로그램은 하위 프로세스입니다.  예를 들어, 웹 사이트를 디버깅할 때 스크립트 프로그램으로 볼 수 있습니다.  스크립팅 엔진 프로세스에 스크립트를 실행 하는 동안 다른 스크립트의 독립이 자체 스레드 집합이 있습니다.  디버그 엔진 \(DE\) 프로그램 및 프로세스 또는 스레드에 첨부합니다.  
  
-   자체 및 실행 되 고, 분리할 수 있는 경우 만든 DE 설명 하려면 연결할 수 있는 프로세스를 식별할 수 있습니다.  프로그램이 있습니다 실행, 중지, 계속, 종료 합니다.  
  
-   모든 스레드를 열거할 수 있습니다.  프로그램 자체 디스어셈블리 스트림을 제공할 수도 있습니다 및 문서의 지정 된 위치에 있는 모든 코드 컨텍스트를 열거할 수 있습니다.  
  
-   표시 되는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 프로그램 연결 된 전에 또는 구현에 따라서는 연결 프로세스의 일부로 만든 인터페이스를.  프로그램 프로세스의 포트를 열거 하는 경우 각 프로그램에 따라 해당 생성 됩니다 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스를 전달 인수로 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md).  디버그 엔진을 만들 수도 있지만 `IDebugProgram2` 프로그램, 이러한 프로그램을 나타내는 인터페이스 프로그램에 따라 노드를 만들 수 없습니다.  `IDebugProgramNode2` 를 DE에서 만든 인터페이스를 사용 실제 디버깅에 대해 포트에서 만든 프로세스에서 실행 중인 프로그램만 알아내는 데 사용 되는 동안.  
  
## 참고 항목  
 [프로세스](../../extensibility/debugger/processes.md)   
 [프로그램 노드](../../extensibility/debugger/program-nodes.md)   
 [모듈](../../extensibility/debugger/modules.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [문서 위치](../../extensibility/debugger/document-position.md)   
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)