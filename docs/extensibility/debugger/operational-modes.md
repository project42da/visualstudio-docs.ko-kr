---
title: "작업 모드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버그 엔진을 모드"
ms.assetid: f69972d0-809d-40df-9da3-04738791391c
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 작업 모드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세 가지 모드에서 IDE를 다음과 같은 방법으로 조작할 수 있습니다 됩니다.  
  
-   [디자인 모드](#vsconoperationalmodesanchor1)  
  
-   [실행 모드](#vsconoperationalmodesanchor2)  
  
-   [중단 모드](#vsconoperationalmodesanchor3)  
  
 사용자 지정 디버그 엔진 \(DE\)을 두이 모드 간을 전환 하는 방법을 구현 결정의 전환 메커니즘을 알고 사용 해야 하는 것입니다.  DE 수도 있고 직접 이러한 모드를 구현할 수 없습니다.  이러한 모드 실제로 사용자의 동작이 나는 DE에서 발생 한 이벤트에 따라 전환 디버그 패키지 모드입니다.  예를 들어, 중단 모드 실행된 모드에서 전환을 간섭 하는 중지 이벤트를 DE에서 여.  나누기 모드 또는 단계 실행 되거나 전환 단계 또는 실행 등의 작업을 수행 하는 사용자가 간섭입니다.  DE 전환에 대 한 자세한 내용은 참조 하십시오. [실행 제어](../../extensibility/debugger/control-of-execution.md).  
  
##  <a name="vsconoperationalmodesanchor1"></a> 디자인 모드  
 디자인 모드로 디버깅 응용 프로그램에 기능을 설정할 수 있습니다 그 동안 Visual Studio 디버깅, nonrunning 상태입니다.  
  
 몇 개의 디버깅 기능 디자인 모드에 있는 동안 사용 됩니다.  개발자가 중단점을 설정 하거나 조사식 식을 만들 수도 있습니다.  DE 로드 되거나 IDE 디자인 모드에 있는 동안 호출 되지 않습니다.  상호는 DE 중단 및 실행 모드에서 수행 됩니다.  
  
##  <a name="vsconoperationalmodesanchor2"></a> 실행 모드  
 실행된 모드는 디버깅 세션 IDE에서 프로그램을 실행 하면 발생 합니다.  응용 프로그램이 종료 될 때까지 중단점이 적중 될 때까지 또는 예외가 throw 될 때까지 실행 됩니다.  DE 전환 디자인 모드를 종료 하려면 응용 프로그램을 실행할 때.  중단점에 도달 하거나 예외가 발생 하는 경우는 DE 중단 모드로 전환 합니다.  
  
##  <a name="vsconoperationalmodesanchor3"></a> 중단 모드  
 중단 모드 디버깅 프로그램의 실행을 일시 중단 되었을 때 발생 합니다.  중단 모드 개발자가 브레이크를 때 응용 프로그램의 스냅샷을 제공 하 고 개발자는 응용 프로그램의 상태를 분석 하 고 변경 하는 방법 응용 프로그램을 실행 합니다.  개발자 볼 및 코드 편집, 검사 또는 데이터 수정, 응용 프로그램 다시 시작, 실행, 종료 또는 같은 지점에서 실행이 계속.  
  
 중단 모드는 DE 동기 중지 이벤트를 보낼 때 입력 합니다.  중지 이벤트 라고도 하는 동기 중지 이벤트 알림 세션 디버그 매니저 \(SDM\) 및 IDE 실행 코드 디버깅 중인 응용 프로그램을 중지 했습니다.  [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 및 [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) 인터페이스 중지 이벤트의 예입니다.  
  
 디버거가 중단 모드에서 실행 또는 실행 모드를 전환 하는 다음 방법 중 하나를 호출 하 여 중지 이벤트가 계속 됩니다.  
  
-   [실행](../../extensibility/debugger/reference/idebugprocess3-execute.md)  
  
-   [단계](../../extensibility/debugger/reference/idebugprocess3-step.md)  
  
-   [계속](../../extensibility/debugger/reference/idebugprocess3-continue.md)  
  
###  <a name="vsconoperationalmodesanchor4"></a> 단계 모드  
 단계 모드 다음 줄의 코드, 또는에, 위 또는 함수 외부로 프로그램을 단계별로 실행할 때 발생 합니다.  이 메서드를 호출 하 여 단계가 실행 됩니다 [단계](../../extensibility/debugger/reference/idebugprocess3-step.md).  이 방법을 사용 해야 `DWORD`지정 s의 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 및 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 열거형으로 입력된 매개 변수입니다.  
  
 프로그램이 성공적으로 다음 줄의 코드 또는 함수에 단계 또는 집합 중단점 또는 커서까지 실행 하는 경우는 DE 자동으로 중단 모드로 다시 전환 됩니다.  
  
## 참고 항목  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)