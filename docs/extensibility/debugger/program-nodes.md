---
title: "프로그램 노드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 컨텍스트를 프로그램 노드"
  - "디버깅 [디버깅 SDK] 프로그램 노드"
  - "프로그램 노드 추가"
  - "대체 프로그램 노드"
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 프로그램 노드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **프로그램 노드의**:  
  
-   프로그램의 간단한 설명이입니다.  
  
-   자체 및 실행 되 고, 분리할 수 있는 경우 생성 되는 디버그 엔진 \(DE\)에 대해 설명 하려면 연결할 수 있는 프로세스를 식별할 수 있습니다.  
  
-   표시 됩니다 있는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 일반적으로 DE 또는 포트에서 만든 인터페이스를 합니다.  프로그램 노드가 추가 된 포트를 호출 하 여 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md).  포트에 프로그램 노드가 추가 되 면이 프로그램이 노드를 나타내는 프로그램을 포함 하 여 프로세스에 추가 됩니다.  
  
 디버그 패키지를 구현에 따라 디버그 세션 시작 잠시 후 프로그램 노드가 해당 프로그램을 만드는 데 사용 됩니다.  그 프로그램에 대 한 프로세스를 쿼리 하는 경우 프로그램을 열거 하는, 프로그램 노드마다 하나씩 있습니다.  
  
 프로그램이 연결 되어 전에 IDE에 대 한 간단한 설명은 프로그램이 필요 합니다.  프로그램 노드에서이 정보를 얻을 수 있습니다.  프로그램에 연결 되 면 IDE 프로그램에서 실행 중인 모든 스레드의 목록 등 보다 자세한 정보를 표시 해야 합니다.  프로그램에서이 정보를 가져옵니다.  
  
## 참고 항목  
 [Programs](../../extensibility/debugger/programs.md)   
 [프로세스](../../extensibility/debugger/processes.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)