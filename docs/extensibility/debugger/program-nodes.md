---
title: "노드 프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6deae60a8e7863e19ec0624ff6452bf41816070
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="program-nodes"></a>프로그램 노드
디버거 아키텍처를 기준으로 한 **프로그램 노드**:  
  
-   프로그램의 간단한 설명이입니다.  
  
-   자체와 프로세스에서 실행 되 고에서 분리 되어 있는 경우 만든 디버그 엔진 (DE)에 대해 설명에 첨부할 수를 식별할 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스를 일반적으로 DE 또는 포트에 의해 만들어집니다. 포트를 호출 하 여 프로그램 노드를 추가 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)합니다. 프로그램 노드 포트에 추가 되 면이 프로그램의 노드가 나타내는 프로그램이 포함 된 프로세스에 추가 됩니다.  
  
 디버그 패키지의 구현에 따라 디버그 세션 시작 된 후에 잠시 프로그램 노드는 해당 프로그램을 만드는 데 사용 됩니다. 프로그램 열거 되는 프로그램에 대 한 프로세스를 쿼리하면 각 프로그램 노드에 대 한 하나 있습니다.  
  
 프로그램에 연결 된, 전에 IDE 프로그램의 간단한 설명만 필요 합니다. 프로그램 노드에서이 정보를 가져올 수 있습니다. 프로그램에 연결 되 면 IDE는 프로그램에서 실행 중인 모든 스레드의 목록 등의 보다 자세한 정보를 표시 해야 합니다. 이 정보는 프로그램 자체에서 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램](../../extensibility/debugger/programs.md)   
 [프로세스](../../extensibility/debugger/processes.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)