---
title: 프로세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e69270c5d90c26cf653ee31b81bcb9f453b814e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="processes"></a>프로세스
디버거 아키텍처를 기준으로 한 **프로세스**:  
  
-   프로그램의 집합에 대 한 컨테이너가입니다. Windows 프로세스 스레드의 집합에 대 한 컨테이너 역할에 밀접 하 게 비슷합니다.  
  
-   이름, 식별자 또는 실제 식별자 자체을 식별할 수 있습니다.  
  
-   실행 중인 모든 프로그램 (및 해당 스레드)를 열거할 수 있습니다.  
  
-   에서 실행 되는 포트 및 포함 된 컴퓨터 자체를 설명할 수 있습니다.  
  
-   새로 만들 수 또는 더 많은 프로그램, 프로그램을 종료 하거나 프로그램을 중지 합니다.  
  
-   로 표시 됩니다는 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) 는 프로세스가 시작 될 때 만들어지는 인터페이스입니다. 두 세션 디버그 관리자 (SDM) 프로세스를 시작할 또는 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)합니다.  
  
 디버그 패키지가 디버그 엔진 (DE) 프로세스에 연결할 수는 호출 하 여 [연결](../../extensibility/debugger/reference/idebugprocess2-attach.md)합니다. 이 DE 처리할 수 있는 프로세스에서 실행 중인 모든 가능한 프로그램에 연결 하는 것을 의미 합니다. 예를 들어, 공용 언어 런타임 DE는 프로세스를 연결 하는 경우 관리 코드를 실행 중인 프로그램에만 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램](../../extensibility/debugger/programs.md)   
 [스레드](../../extensibility/debugger/threads.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [패키지를 디버그 합니다.](../../extensibility/debugger/debug-package.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)