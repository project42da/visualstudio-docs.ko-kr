---
title: "프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e34dbcf9c19b5e8e7a16d2f409159597670cb8cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="programs"></a>Programs
디버거 아키텍처를 기준으로 한 **프로그램**:  
  
-   스레드의 집합 및 모듈의 집합 모두에 대 한 컨테이너가입니다. 프로그램에 Windows 운영 체제가 없는 단일 예를 들어 있습니다.  
  
     프로그램은 하위 프로세스의 종류입니다. 예를 들어 웹 사이트를 디버깅 하는 스크립트를 프로그램으로 볼 수 있습니다. 스크립트 스크립팅 엔진 프로세스에서 실행 되는 동안 다른 스크립트와 무관 것도 고유한 스레드입니다. 디버그 엔진 (DE)는 프로그램 아니라에 프로세스 또는 스레드를 연결합니다.  
  
-   자체와 프로세스에서 실행 되 고에서 분리 되어 있는 경우 만든 DE 설명에 첨부할 수를 식별할 수 있습니다. 프로그램 실행, 중지, 계속 해 서 수를 종료 합니다.  
  
-   모든 스레드를 열거할 수 있습니다. 프로그램 제공할 수도 있습니다. 고유한 디스어셈블리 스트림 및 지정한 문서 위치의 모든 코드 컨텍스트를 열거할 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 프로그램을 연결 하면 뷰어에서 전이나 구현에 따라 연결 프로세스의 일부로 만든 인터페이스입니다. 각 프로그램 해당에 따른 생성은 포트 프로그램 프로세스를 열거할 경우 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스에 대 한 인수로 전달 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)합니다. 디버그 엔진을 만들 수도 동안 `IDebugProgram2` 프로그램 노드에 따라 프로그램, 이러한 프로그램을 나타내는 인터페이스 생성 되지 않습니다. `IDebugProgramNode2` 는 DE 하 여 만든 인터페이스는 포트를 통해 만든 검색 하는 프로세스에서 실행 중인 프로그램에 대해서만 사용 되지만 실제 디버깅을 위해 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
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