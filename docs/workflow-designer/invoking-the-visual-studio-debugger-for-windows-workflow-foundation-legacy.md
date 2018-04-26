---
title: Visual Studio Debugger for Windows Workflow Foundation (레거시)를 호출 하는 워크플로 디자이너-
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a326f8b6dc482c2adfc2caba797c38094a99f8c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Visual Studio Debugger for Windows Workflow Foundation 호출(레거시)

이 항목에서는 설명 방법을 레거시 Windows 워크플로 디자이너에서 Windows WF (Workflow Foundation) 응용 프로그램을 디버깅 하려면 Visual Studio 디버거를 사용 합니다. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

일반적으로 레거시 워크플로를 디버깅하는 과정은 다른 Visual Studio 프로그래밍 언어로 작성된 프로그램을 디버깅하는 과정과 같습니다. 다음과 같은 방법으로 Visual Studio Debugger for Windows Workflow Foundation을 시작할 수 있습니다.

-   선택 **프로세스에 연결** 에 **디버그** 메뉴를 사용 가능한 프로세스에서 실행 중인 워크플로 인스턴스를 선택 합니다.

-   키를 눌러 **F5** 는 워크플로 인스턴스 실행을 시작 하거나 중단점이 적중 된 후 실행을 계속 합니다.

## <a name="stepping-through-code"></a>단계별 코드 실행

디버거는 가장 일반적인 디버깅 절차 중 하나인, 한 번에 한 줄씩 코드를 실행하는 단계별 실행을 지원합니다. 단계별 코드 실행 명령에는 세 가지가 있습니다.

-   **단계에서**: 사용 하 여 활동 한 단계씩 실행할 수 **F11**합니다. 디버거는 정의된 임의의 처리기에서 한 단계씩 코드를 실행합니다. 정의된 처리기가 없으면 해당 활동을 프로시저 단위로 실행합니다. 다른 활동이 포함된 복합 활동의 경우 실행 중인 첫 번째 활동을 단계적으로 실행합니다. 디자이너에서 코드 처리기에 한 단계씩 실행에서 다음과 같은 작업에 지원 되지 않습니다: **IfElseActivity**, **WhileActivity**, **ConditionedActivityGroup**, 또는 **ReplicatorActivity**합니다. 이러한 활동과 연결된 처리기를 디버깅하려면 코드에 명시적인 중단점을 넣어야 합니다.

-   **프로시저 나가기**: 사용 하 여 활동에서 나갈 수 있습니다 **shift-f11**합니다. 활동에서 나가기를 수행하면 현재 활동 및 모든 형제 활동이 완료 시까지 실행됩니다. 그런 다음 디버거는 현재 활동의 부모에서 중단합니다. 코드 처리기에서 나갈 때 디버거는 처리기가 연결된 활동에서 중단합니다.

-   **프로시저 단위 실행**: 사용 하 여 활동을 건너뛸 수 **F10**합니다. 복합 활동을 프로시저 단위로 실행할 때 디버거는 복합 활동의 첫 번째 실행 가능 자식에서 중단합니다. 와 같은 비 복합을 건너뛸 경우는 **CodeActivity** 활동, 디버거를와 연결 된 처리기의 활동 및 나누기 다음 활동에서 실행 합니다. 실행되는 활동이 복합 활동 중 마지막 자식 활동인 경우, 실행 후에 디버거는 부모 활동에서 중단합니다.

## <a name="attaching-to-a-process"></a>프로세스에 연결
 프로세스에 연결 하 여 워크플로 디버깅 하려면에서 사용할 수 있는 프로세스를 선택는 **사용 가능한 프로세스** 목록 상자에는 **프로세스에 연결** 대화 상자. 경우 **자동: 워크플로 코드** 에 표시 되지 않습니다는 **연결할** 텍스트 상자의 클릭 **선택**합니다. 에 **코드 형식 선택** 대화 상자를 클릭 **다음 코드 형식 디버깅** 선택 **워크플로**합니다. 클릭 **확인** 클릭 **연결**합니다.

## <a name="debugging-with-f5"></a>F5 키를 사용한 디버깅
 워크플로 DLL 프로젝트의 워크플로 디버깅 하려면 Visual Studio 솔루션 시작 프로젝트로 설정 해야 워크플로 호스트 응용 프로그램과 워크플로 DLL에에서 있는 경우 다른 Visual Studio 프로젝트 예를 들어, 워크플로 활동 라이브러리를 사용 하는 경우 사용 하 여 **F5**합니다. 경로 워크플로 DLL 프로젝트에서 호스트 응용 프로그램에 설정 해야 **시작 외부 프로그램** 속성입니다.

 솔루션 탐색기에서 시작 프로젝트를 설정 하려면 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다. 호스트에 경로 설정 하는 **시작 외부 프로그램** 속성을 워크플로 프로젝트를 두 번 클릭 **속성** 에서 솔루션 탐색기를 선택 하는 노드는 **디버그** 탭 합니다. 아래 **시작 작업**선택, **시작 외부 프로그램** 를 디버깅 하려면 워크플로 호스트 하는.exe 파일의 경로 입력 합니다.

 Visual Studio 디버거만 디버깅;에 대 한 호출 됩니다는 호스트 응용 프로그램을 시작 프로젝트로 설정 Visual Studio Debugger for Windows Workflow Foundation 호출 되지 않습니다. Visual Studio 디버거가 사용되는 경우 C# 또는 Visual Basic 코드 중단점만 적중됩니다. 워크플로 디자이너에 설정된 중단점은 적중되지 않습니다. 예를 들어에 설정한 중단점은 <xref:System.Workflow.Activities.ParallelActivity> 는 Visual Studio Debugger for Windows Workflow Foundation를 사용 되지만 Visual Studio 디버거를 사용할 때가 아니라 디자이너의 활동에 도달 합니다.

## <a name="see-also"></a>참고자료

- [방법: 워크플로에 중단점 설정(레거시)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)