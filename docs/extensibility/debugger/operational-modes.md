---
title: 작업 모드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, modes
ms.assetid: f69972d0-809d-40df-9da3-04738791391c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72ae5a36f9f0547635872f5c8ebe30f2f3c53d5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="operational-modes"></a>작업 모드
세 가지 모드는 IDE 작동할 수, 다음과 같습니다.  
  
-   [디자인 모드](#vsconoperationalmodesanchor1)  
  
-   [실행 모드](#vsconoperationalmodesanchor2)  
  
-   [중단 모드](#vsconoperationalmodesanchor3)  
  
 사용자 지정 디버그 엔진 (DE)을 통해 이러한 모드 간에 전환 하는 방법을 전환 메커니즘에 익숙해지는 것을 요구 하는 구현을 결정입니다. DE 수도 있고 그렇지 직접 이러한 모드를 구현 하지 않을 수 있습니다. 이러한 모드는 실제로 디버그 패키지 모드 전환 하는 사용자 동작 또는 이벤트는 DE에서 기반 합니다. 예를 들어 실행된 모드에서 중단 모드로 전환은 DE의 중지 이벤트에서 발생 시킨 됩니다. 단계 또는 Execute 같은 작업을 수행 하는 사용자가 모드 또는 단계 모드 실행을 중단에서 전환을 발생 시킨 됩니다. DE 전환에 대 한 자세한 내용은 참조 [실행 제어](../../extensibility/debugger/control-of-execution.md)합니다.  
  
##  <a name="vsconoperationalmodesanchor1"></a> 디자인 모드  
 디자인 모드는 디버깅 응용 프로그램의 기능을 설정할 수 있으며이 기간 동안 Visual Studio 디버깅의 nonrunning 상태입니다.  
  
 몇 가지 디버깅만 기능을 사용 하 여 디자인 모드에 있는 동안 합니다. 개발자는 중단점을 설정 하거나 조사식 식을 만들 수도 있습니다. DE 로드 되거나 IDE 디자인 모드에 있는 동안 호출 되지 않습니다. DE와의 상호 작용 하는 동안 실행 및 중단 모드에만 수행이 됩니다.  
  
##  <a name="vsconoperationalmodesanchor2"></a> 실행 모드  
 실행된 모드는 IDE의 디버깅 세션에서 프로그램 실행 될 때 발생 합니다. 중단점 적중 될 때까지 또는 예외가 throw 될 때까지 응용 프로그램이 종료 될 때까지 실행 합니다. 응용 프로그램 종료를 디자인 모드로 DE 전환에 실행 될 때 중단점에 또는 예외가 throw 되는 DE 중단 모드로 전환 됩니다.  
  
##  <a name="vsconoperationalmodesanchor3"></a> 중단 모드  
 중단 모드에는 디버깅 프로그램의 실행을 일시 중단 되 면 발생 합니다. 중단 모드 개발자 나누기 시 응용 프로그램의 스냅숏을 제공 하 고 개발자가 응용 프로그램의 상태를 분석 하 고 응용 프로그램이 실행 되는 방식을 변경할 수 있습니다. 개발자 수를 보고 코드 편집, 검사 또는 수정 데이터, 응용 프로그램을 다시 시작, 실행을 종료 하거나 같은 지점에서 실행을 계속 합니다.  
  
 중단 모드는 DE 동기 stopping 이벤트를 보낼 때 입력 됩니다. 중지 이벤트를를 호출 또한 동기 중지 이벤트를 알리는 세션 디버그 관리자 (SDM) 및 IDE 디버깅 중인 응용 프로그램 코드 실행을 중지 합니다. [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 및 [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) 인터페이스는 stopping 이벤트의 예입니다.  
  
 중지 이벤트를 실행 하거나 모드 단계 중단 모드에서 디버거를 전환 하는 다음 메서드 중 하나를 호출 하 여 계속 됩니다.  
  
-   [실행](../../extensibility/debugger/reference/idebugprocess3-execute.md)  
  
-   [Step](../../extensibility/debugger/reference/idebugprocess3-step.md)  
  
-   [Continue](../../extensibility/debugger/reference/idebugprocess3-continue.md)  
  
###  <a name="vsconoperationalmodesanchor4"></a> 단계 모드  
 단계 모드 코드 또는 into, 또는 함수에서 다음 줄으로 이동 하는 경우에 발생 합니다. 메서드를 호출 하 여 실행 되는 단계의 [단계](../../extensibility/debugger/reference/idebugprocess3-step.md)합니다. 이 방법을 사용 하려면 `DWORD`지정 하는 s는 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 및 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 입력된 매개 변수로 열거형입니다.  
  
 를 성공적으로 함수로 또는 코드의 다음 줄으로 이동 하거나 또는 집합 중단점 커서까지 실행 되는 DE 중단 모드에 다시 자동으로 전환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)