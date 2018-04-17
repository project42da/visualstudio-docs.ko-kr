---
title: 스레드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a2754d3b1b15771f876855e7ca7d1dc510748308
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="threads"></a>스레드
디버거 아키텍처를 기준으로 한 **스레드**:  
  
-   계산의 기본 단위가입니다. 스레드를 순차적으로 다음 하나의 코드 컨텍스트를 이동 하는 단일 호출 스택, 컨텍스트 내에서 명령을 실행 합니다.  
  
-   자체와 프로그램을에서 실행 되 고 및 고 될 수 라는, 일시 중단, 다시 시작을 식별할 수 있습니다. 스레드에서 연결 된 스택 프레임을 열거할 수 있고 일부 조건에서는 다른 스택 프레임으로 이동할 수 있습니다. 스택 프레임의 컨텍스트를 지정 하는, 스레드 수 반환은 연결된의 논리적 스레드를 있는 경우. 스레드는 IDE의 스레드 창에 표시 될 수 있는 일시 중단 횟수가 등의 속성을 갖고 있습니다.  
  
-   로 표시 됩니다는 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) 인터페이스를 일반적으로 프로그램 실행의 결과로 가상 컴퓨터 또는 디버그 엔진 (DE)에 의해 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램](../../extensibility/debugger/programs.md)   
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [세션 디버그 관리자](../../extensibility/debugger/session-debug-manager.md)