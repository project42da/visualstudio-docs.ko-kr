---
title: 디버거 이벤트 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3960d464b1a6d44fb77eba23cd518fea1f2e5a39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="calling-debugger-events"></a>호출 디버거 이벤트
디버깅 세션에 이벤트는 특정 순서로 발생 합니다.  
  
## <a name="discussion"></a>토론  
 디버그 엔진 (DE)와 세션 디버그 관리자 (SDM) 간의 호출 패턴을 이해 하려면 다음 호출의 순서를 나타내는 일반적인 디버깅 세션에서 발생 하는 이벤트:  
  
1.  [연결 및 분리 하는 프로그램](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [디버거 시작](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [프로그램 종료](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [중단점을 만듭니다.](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [중단점에 바인딩합니다 또는 언바운드 되 고](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [중단점 오류](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [중단점](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [중단점 삭제](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [중단 모드](../../extensibility/debugger/entering-break-mode.md)  
  
10. [중단 모드에서 단계별 실행](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [중단 모드에 있는 식 계산](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [예외 처리](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)