---
title: "관리 코드 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6710f5065622161b60e7a40cc136cdb2ba2b0b72
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="debugging-managed-code"></a>관리 코드 디버깅

이 단원에서는 Visual Basic, C# 및 C++ 등 공용 언어 런타임을 대상으로 하는 언어로 작성된 관리되는 응용 프로그램의 일반적인 디버깅 문제와 기술에 대해 설명합니다. 이 단원에서 설명하는 기술은 높은 수준의 기술입니다. 자세한 내용은 참조 [디버거를 사용 하 여](../debugger/debugger-basics.md)합니다.

## <a name="in-this-section"></a>섹션 내용

[출력 창에 표시되는 진단 메시지](../debugger/diagnostic-messages-in-the-output-window.md)  
설명의 <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스는 런타임에 메시지를 작성할 수 있습니다는 **출력** 창. 이러한 클래스에는 실행을 중단하지 않고 정보를 출력하는 출력 메서드와 지정된 조건이 실패할 경우 실행을 중단하고 정보를 출력하는 출력 메서드가 포함되어 있습니다.

[관리 코드에 어설션 사용](../debugger/assertions-in-managed-code.md)  
`Assert` 메서드에 인수로 지정하는 조건을 테스트하는 관리 코드의 어설션에 대해 설명합니다. 또한 예제 코드, <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스 메서드의 사용 정보, 코드의 디버그 및 릴리스 버전에 대한 고려 사항, 의도하지 않은 연산, 어설션 인수, 어설션 동작 사용자 지정, 구성 파일 등의 내용을 제공합니다.

[Visual Basic의 Stop 문](../debugger/stop-statements-in-visual-basic.md)  
중단점을 설정하는 대신 사용할 수 있는 `Stop` 문에 대해 설명합니다. `Stop` 문과 `End` 문을 비교하고 `Stop` 문과 `Assert` 문을 비교하여 살펴볼 뿐만 아니라 예제 코드도 제공합니다.

[연습: Windows Form 디버그](../debugger/walkthrough-debugging-a-windows-form.md)  
Windows Form 만들기 및 Windows Form 디버깅을 위한 단계별 지침을 제공합니다. 관리되는 Windows 응용 프로그램의 표준 구성 요소인 Windows Form은 가장 일반적인 형태의 관리되는 응용 프로그램 중 하나입니다. 이 연습에서는 Visual C#과 Visual Basic을 사용하지만 C++로 Windows Form을 만드는 방법도 대체로 비슷합니다.

[OnStart 메서드 디버깅](../debugger/how-to-debug-the-onstart-method.md)  
관리되는 Windows 서비스의 `OnStart` 메서드를 디버깅할 수 있는 코드 예제를 제공합니다. Windows 서비스의 `OnStart` 메서드를 디버깅하려면 몇 줄의 코드를 추가하여 서비스를 시뮬레이션해야 합니다.

[혼합 모드 디버깅](../debugger/debugging-mixed-mode-applications.md)  
혼합 모드 응용 프로그램을 디버깅하는 방법에 대해 설명합니다. 혼합 모드 응용 프로그램은 네이티브 코드와 관리 코드가 결합된 응용 프로그램입니다.

[오류: 시스템에 커널 디버거가 사용 중이므로 디버깅을 할 수 없습니다.](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
관리 되는 코드를 디버깅 하려고 할 경우에 발생 하는 오류 메시지에 설명 된 [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], 또는 디버그 모드에서 시작 된 Windows NT 시스템입니다.

[JIT 최적화 및 디버깅](../debugger/jit-optimization-and-debugging.md)  
디버깅 시 JIT 최적화의 효과에 대해 설명합니다.

[LINQ 및 DLINQ 디버깅](../debugger/debugging-linq.md)  
LINQ 쿼리에 대한 디버깅 기술에 대해 설명합니다.

[연습: 병렬 응용 프로그램 디버그](../debugger/walkthrough-debugging-a-parallel-application.md)  
사용 하는 방법에 설명 된 **병렬 작업** 및 **병렬 스택** 도구 창을 병렬 응용 프로그램의 디버깅.

## <a name="related-sections"></a>관련 단원

[IntelliTrace](../debugger/intellitrace.md) IntelliTrace로 응용 프로그램의 실행 내역을 기록 하 여 빠르고 쉽게 버그를 찾습니다. 기록된 이벤트 및 호출에서 앞뒤로 이동하며 주요 시점의 응용 프로그램 상태를 확인합니다. 여러 중단점을 설정하거나 자주 응용 프로그램을 다시 시작하지 않고 코드를 디버깅합니다. Visual Studio Enterprise를 필요합니다.

[응용 프로그램 추적 및 조율](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
실행 중인 응용 프로그램의 실행을 모니터링하는 방법인 추적과 코드의 전략적 위치에 추적 문을 배치하는 방법인 조율에 대해 설명합니다. 이 항목에서는 계측 및 추적, 추적 스위치, 추적 수신기, 응용 프로그램의 코드 추적, 응용 프로그램 코드에 추적 문 추가, <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace>를 사용하는 조건부 컴파일 등을 소개하는 정보로 연결되는 링크도 제공합니다.

[/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)  
추가 하는 링커 옵션을 설명 <xref:System.Diagnostics.DebuggableAttribute> c + +로 작성 된 코드입니다. 이 특성은 C++를 사용한 연결 등의 디버깅 기능을 사용하는 데 필요합니다.

[Windows 서비스 응용 프로그램 디버깅](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)  
설정, 프로세스에 연결, 서비스의 `OnStart` 메서드 코드 및 Main 메서드 코드 디버깅, 중단점 설정 그리고 서비스 제어 관리자를 사용한 서비스 시작, 중지, 일시 중지 및 계속 등을 포함하여 Windows 서비스 응용 프로그램을 디버깅할 때 고려해야 할 사항에 대해 설명합니다.

[디버깅 및 프로 파일링](/dotnet/framework/debug-trace-profile/index)  
.NET Framework 응용 프로그램의 디버깅과 구성 요구 사항에 대해 설명합니다.

[스크립트 및 웹 응용 프로그램 디버깅](../debugger/debugging-web-applications-and-script.md)  
스크립트 및 웹 응용 프로그램을 디버깅할 때 발생할 수 있는 일반적인 디버깅 문제와 기술에 대해 설명합니다.

[Visual Studio 2015 디버거의 새로운 기능](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)  
이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 릴리스에 새로 추가된 디버깅 기능에 대해 설명합니다.

[디버깅 홈 페이지](../debugger/debugger-feature-tour.md)  
자세한 디버깅 설명서 단원으로 연결되는 링크를 제공합니다. 이 정보에는 디버거의 새로운 기능, 설정 및 준비, 중단점, 예외 처리, 편집 및 계속, 관리 코드 디버깅, Visual C++ 프로젝트 디버깅, COM 및 ActiveX 디버깅, DLL 디버깅, SQL 디버깅, 사용자 인터페이스 참조 등이 포함됩니다.

## <a name="see-also"></a>참고 항목

[연습: 사용자 지정 Windows Forms 컨트롤 디버깅 디자인 타임에](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
[디버거 보안](../debugger/debugger-security.md)
[Visual Studio의 디버깅](../debugger/index.md) 
 [ 디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)