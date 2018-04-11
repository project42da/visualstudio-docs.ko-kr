---
title: Python 코드 디버깅 | Microsoft Docs
description: 중단점 설정, 단계별 실행, 값 검사, 예외 확인, 대화형 창에서 디버깅을 포함하여 특히 Python 코드에 대한 Visual Studio의 디버깅 기능 연습입니다.
ms.custom: ''
ms.date: 03/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 850fb940b35e3fe988b8ecf8dc483ed489f985db
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2018
---
# <a name="debugging-your-python-code"></a>Python 코드 디버깅

Visual Studio에서는 실행 중인 프로세스에 연결하고, 조사식 및 직접 실행 창에서 식을 계산하고, 지역 변수, 중단점, 문 단계별 실행/프로시저 나가기/프로시저 단위 실행, 다음 문 설정 등을 검사하는 작업을 포함한 포괄적인 디버깅 환경을 Python에 제공합니다.

또한 다음 시나리오별 디버깅 문서를 참조하세요.

- [Linux 원격 디버깅](debugging-python-code-on-remote-linux-machines.md)
- [Azure 원격 디버깅](debugging-remote-python-code-on-azure.md)
- [Python/C++ 혼합 모드 디버깅](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- [혼합 모드 디버깅 기호](debugging-symbols-for-mixed-mode-c-cpp-python.md)

|   |   |
|---|---|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | Python 디버깅 데모 [비디오(Microsoft Virtual Academy)를 시청](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Debugging-Python-Ep5dp5LWE_3805918567)하세요(3분 32초).|

<a name="debugging-without-a-project"></a>

> [!Tip]
> Visual Studio의 Python은 프로젝트 없이 디버깅을 지원합니다. 편집기에서 마우스 오른쪽 단추를 클릭하여 독립 실행형 Python 파일을 열고 **디버깅 시작**을 선택하면 Visual Studio가 전역 기본 환경([Python 환경](managing-python-environments-in-visual-studio.md) 참조)에서 인수 없이 스크립트를 실행합니다. 하지만 이때부터 디버깅을 전적으로 지원합니다.
>
> 환경 및 인수를 제어하려면 코드에 대한 프로젝트를 만듭니다. 이 작업은 [기존 Python 코드에서](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) 프로젝트 템플릿으로 쉽게 수행할 수 있습니다.

<a name="debugging-with-a-project"></a>

## <a name="basic-debugging"></a>기본적인 디버깅

기본적인 디버깅 워크플로에는 다음 섹션에서 설명한 대로 중단점 설정, 단계별 코드 실행, 값 검사 및 예외 처리가 포함됩니다.

디버깅 세션은 **디버그 > 디버깅 시작** 명령, 도구 모음의 **시작** 단추 또는 F5 키로 시작됩니다. 이러한 작업은 프로젝트의 활성 환경 및 프로젝트 속성([프로젝트 디버깅 옵션](#project-debugging-options) 참조)에 지정된 명령줄 인수 또는 검색 경로가 포함된 프로젝트의 시작 파일(솔루션 탐색기에서 굵게 표시됨)을 실행합니다. **Visual Studio 2017 버전 15.6** 이상에서는 시작 파일이 설정되지 않은 경우 경고가 표시되고, 이전 버전에서는 Python 인터프리터를 실행하는 출력 창이 열리거나 출력 창이 잠시 표시되었다가 사라집니다. 어떤 경우든, 해당 파일을 마우스 오른쪽 단추로 클릭하고 **시작 파일로 설정**을 선택합니다.

> [!Note]
> 디버거는 프로젝트에 대해 항상 활성 Python 환경으로 시작합니다. 환경을 변경하려면 [프로젝트에 대한 Python 환경 선택](selecting-a-python-environment-for-a-project.md)에 설명된 대로 다른 환경을 활성화합니다.

### <a name="breakpoints"></a>중단점

중단점은 프로그램 상태를 검사할 수 있도록 표시된 지점에서 코드 실행을 중지합니다. 코드 편집기의 왼쪽 여백을 클릭하거나 코드 줄을 마우스 오른쪽 단추로 클릭하고 **중단점 > 중단점 삽입**을 선택하여 중단점을 설정합니다. 각 행에 중단점과 함께 빨간색 점이 표시됩니다.

![Visual Studio의 중단점](media/debugging-breakpoints.png)

빨간색 점을 클릭하거나 코드 줄을 마우스 오른쪽 단추로 클릭하고 **중단점 > 중단점 삭제**를 선택하면 중단점이 제거됩니다. 제거하는 대신, **중단점 > 중단점 사용 안 함** 명령을 통해 사용하지 않도록 설정할 수도 있습니다.

> [!Note]
> Python의 일부 중단점은 다른 프로그래밍 언어에 익숙한 개발자에게 놀라운 경험이 될 수 있습니다. Python에서 전체 파일은 실행 가능한 코드이므로 최상위 클래스 또는 함수 정의를 처리하기 위해 로드될 때 Python에서 해당 파일을 실행합니다. 중단점이 설정되면 디버거에서 도중에 클래스 선언을 통해 중단되는 것을 알 수 있습니다. 이 동작은 때때로 놀랍긴 해도 올바른 동작입니다.

변수가 특정 값이나 값 범위에 도달했을 때만 중단하는 것과 같이 중단점을 트리거하는 조건을 사용자 지정할 수 있습니다. 조건을 설정하려면 중단점의 빨간색 점을 마우스 오른쪽 단추로 클릭하고 **조건**을 선택한 다음 Python 코드를 사용하여 식을 만듭니다. Visual Studio의 이 기능에 대한 자세한 내용은 [중단점 조건](../debugger/using-breakpoints.md#breakpoint-conditions)을 참조하세요.

조건을 설정할 때 **작업**을 설정하고, 출력 창에 기록할 메시지를 만들고, 필요에 따라 자동으로 계속 실행할 수도 있습니다. 메시지를 기록하면 로깅 코드를 응용 프로그램에 직접 추가하지 않고 *추적점*이란 것이 생성됩니다.

![중단점이 있는 추적점 만들기](media/debugging-tracepoint.png)

### <a name="stepping-through-code"></a>단계별 코드 실행

중단점에서 중지되면 다시 중지되기 전에 코드를 단계별로 실행하거나 코드 블록을 실행하는 다양한 방법이 있습니다. 이러한 명령은 위쪽의 디버그 도구 모음, **디버그** 메뉴, 코드 편집기에서 마우스 오른쪽 단추로 클릭하는 상황에 맞는 메뉴 및 바로 가기 키 등을 포함하여 다양한 위치에서 사용할 수 있습니다(모든 위치에 모든 명령이 있는 것은 아님).

| 기능 | 키 입력 | 설명 |
| --- | --- | --- |
| Continue | F5 | 다음 중단점에 도달할 때까지 코드를 실행합니다. |
| 한 단계씩 코드 실행 | F11 | 다음 문을 실행하고 중지합니다. 다음 문이 함수 호출인 경우 디버거는 호출되는 함수의 첫 번째 줄에서 중지합니다. |
| 프로시저 단위 실행 | F10 | 함수 호출(모든 코드 실행) 및 반환 값 적용을 포함하여 다음 문을 실행합니다. 프로시저 단위 실행을 사용하면 디버그할 필요가 없는 함수를 쉽게 건너뛸 수 있습니다. |
| 프로시저 나가기 | Shift+F11 | 현재 함수가 끝날 때까지 코드를 실행한 후 호출하는 문으로 이동합니다.  이 명령은 현재 함수의 나머지 부분을 디버그할 필요가 없을 때 유용합니다. |
| 커서까지 실행 | Ctrl+F10 | 편집기에서 캐럿의 위치까지 코드를 실행합니다. 이 명령을 사용하면 디버그할 필요가 없는 코드 세그먼트를 쉽게 건너뛸 수 있습니다. |
| 다음 문 설정 | Ctrl+Shift+F10 | 코드의 현재 실행 지점을 캐럿 위치로 변경합니다. 이 명령을 사용하면 코드에 결함이 있거나 원하지 않는 부작용이 발생했을 때와 같은 경우 실행되지 않도록 코드 세그먼트를 생략할 수 있습니다. |
| 다음 문 표시 | Alt+Num * | 실행할 다음 문으로 돌아갑니다. 이 명령은 코드를 둘러보았지만 디버거가 중지된 위치가 기억나지 않는 경우에 매우 유용합니다. |

### <a name="inspecting-and-modifying-values"></a>값 검사 및 수정

디버거에서 중지되면 변수 값을 검사하고 수정할 수 있습니다. [조사식] 창을 사용하여 개별 변수와 사용자 지정 식을 모니터링할 수도 있습니다. 자세한 내용은 [변수 검사](../debugger/getting-started-with-the-debugger.md#inspect-variables-with-the-autos-and-locals-windows)를 참조하세요.

DataTips를 사용하여 값을 보려면 편집기에서 변수 위로 마우스를 이동하면 됩니다. 값을 클릭하여 변경할 수 있습니다.

![디버거의 DataTips](media/debugging-quick-tips.png)

[자동] 창(**디버그 > 창 > 자동**)에는 현재 문에 가까운 변수와 식이 포함되어 있습니다. 값 열을 두 번 클릭하거나 선택하고 F2 키를 눌러 값을 편집할 수 있습니다.

![디버거의 자동 창](media/debugging-autos-window.png)

[지역] 창(**디버그 > 창 > 지역**)에는 현재 범위에 있는 모든 변수가 표시되며 다시 편집될 수 있습니다.

![디버거의 지역 창](media/debugging-locals-window.png)

[자동] 및 [지역] 창 사용에 대한 자세한 내용은 [자동 및 지역 창에서 변수 검사](../debugger/autos-and-locals-windows.md)를 참조하세요.

[조사식] 창(**디버그 > 창 > 조사식 > 조사식 1-4**)을 사용하면 임의의 Python 식을 입력하고 결과를 볼 수 있습니다. 식은 각 단계마다 다시 계산됩니다.

![디버거의 조사식 창](media/debugging-watch-window.png)

조사식 사용에 대한 자세한 내용은 [조사식 창과 간략한 조사식 창을 사용하여 변수에 대한 조사식 설정](../debugger/watch-and-quickwatch-windows.md)을 참조하세요.

문자열 값(`str`, `unicode`, `bytes` 및 `bytearray`는 모두 이 목적을 위한 문자열로 간주됨)을 검사하면 값의 오른쪽에 돋보기 모양 아이콘이 나타납니다. 아이콘을 클릭하면 팝업 대화 상자에서 따옴표가 없는 문자열 값이 줄 바꿈 및 스크롤과 함께 표시되며, 긴 문자열에 유용합니다. 또한 아이콘의 드롭다운 화살표를 선택하면 일반 텍스트, HTML, XML 및 JSON 시각화를 선택할 수 있습니다.

![문자열 시각화 도우미](media/debugging-string-visualizers.png)

HTML, XML 및 JSON 시각화는 구문 강조 표시 및 트리 보기가 있는 별도의 팝업 창에 표시됩니다.

### <a name="exceptions"></a>예외

디버그하는 동안 프로그램에서 오류가 발생하지만 이 오류에 대한 예외 처리기가 없으면 디버거가 예외 지점에서 중단됩니다.

![예외 팝업](media/debugging-exception-popup.png)

이 지점에서 호출 스택을 포함하여 프로그램 상태를 검사할 수 있습니다. 그러나 코드를 단계별로 실행하려고 하면 예외를 처리하거나 프로그램을 종료할 때까지 예외가 계속 throw됩니다.

**디버그 > 창 > 예외 설정** 메뉴 명령은 **Python 예외**를 확장할 수 있는 창을 엽니다.

![예외 창](media/debugging-exception-settings.png)

각 예외의 확인란은 예외가 발생했을 때 디버거가 *항상* 중단되는지 여부를 제어합니다. 특정 예외에 대해 더 자주 중단하려는 경우 이 상자를 선택합니다.

기본적으로 소스 코드에서 예외 처리기를 찾을 수 없는 경우 대부분의 예외로 인해 중단됩니다. 이 동작을 변경하려면 예외를 마우스 오른쪽 단추로 클릭하고 **사용자 코드에서 처리되지 않은 경우 계속**을 선택하거나 선택 취소합니다. 예외로 인해 발생하는 중단을 줄이려면 이 상자를 선택 취소합니다.

이 목록에 표시되지 않은 예외를 구성하려면 **추가** 단추를 클릭하여 추가합니다. 이름은 예외의 전체 이름과 일치해야 합니다.

## <a name="project-debugging-options"></a>프로젝트 디버깅 옵션

기본적으로 디버거는 표준 Python 시작 관리자를 통해 명령줄 인수와 다른 특수 경로나 조건이 없는 프로그램을 시작합니다. 시작 옵션은 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하고 **디버그** 탭을 선택하여 액세스한 프로젝트의 디버그 속성을 통해 변경됩니다.

![프로젝트 디버그 속성](media/debugging-project-properties.png)

### <a name="launch-mode-options"></a>실행 모드 옵션

| 옵션 | 설명 |
| --- | --- |
| 표준 Python 시작 관리자 | CPython, IronPython 및 변형(예: Stackless Python)과 호환되는 휴대용 Python으로 작성된 디버깅 코드를 사용합니다. 순수 Python 코드를 디버그하기 위한 최상의 환경을 제공합니다. 실행 중인 `python.exe` 프로세스에 연결하면 이 시작 관리자가 사용됩니다. 이 시작 관리자는 CPython에 대한 [혼합 모드 디버깅](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)도 제공하므로 C/C++ 코드와 Python 코드 간에 단계별로 완벽하게 실행할 수 있습니다. |
| 웹 시작 관리자 | 시작 시 기본 브라우저를 시작하고 템플릿 디버깅을 활성화합니다. 자세한 내용은 [웹 템플릿 디버깅](python-web-application-project-templates.md#debugging) 섹션을 참조하세요. |
| Django 웹 시작 관리자 | 웹 시작 관리자와 동일하며, 이전 버전과의 호환성을 위해서만 표시됩니다. |
| IronPython(.NET) 시작 관리자 | IronPython에서만 작동하는 .NET 디버거를 사용하지만 C# 및 VB를 포함한 모든 .NET 언어 프로젝트 간 단계별 실행을 허용합니다. IronPython을 호스팅하는 실행 중인 .NET 프로세스에 연결하는 경우 이 시작 관리자가 사용됩니다. |

### <a name="run-options-search-paths-startup-arguments-and-environment-variables"></a>실행 옵션(검색 경로, 시작 인수 및 환경 변수)

| 옵션 | 설명 |
| --- | --- |
| 검색 경로 | 이러한 값은 솔루션 탐색기에서 프로젝트의 검색 경로 노드에 표시되는 값과 일치합니다. 여기서 해당 값을 수정할 수는 있지만, 폴더를 탐색하고 경로를 상대 형식으로 자동 변환할 수 있는 [솔루션 탐색기]를 사용하는 것이 더 쉽습니다. |
| 스크립트 인수 | 이러한 인수는 스크립트를 시작하는 데 사용되는 명령에 추가되며, 스크립트의 파일 이름 뒤에 표시됩니다. 스크립트에서 첫 번째 항목은 `sys.argv[1]`, 두 번째 항목은 `sys.argv[2]` 등으로 사용할 수 있습니다. |
| 인터프리터 인수 | 이러한 인수는 시작 관리자 명령줄에서 스크립트의 이름 앞에 추가됩니다. 여기서 공통 인수는 경고를 제어하기 위한 `-W ...`, 프로그램을 약간 최적화하기 위한 `-O` 및 버퍼링되지 않은 IO를 사용하기 위한 `-u`입니다. IronPython 사용자는 이 필드를 사용하여 `-X:Frames` 또는 `-X:MTA`와 같은 `-X` 옵션을 전달할 수 있습니다. |
| 인터프리터 경로 | 현재 환경과 연결된 경로를 재정의합니다.  값은 비표준 인터프리터로 스크립트를 시작하는 데 유용할 수 있습니다. |
| 환경 변수 | 이 여러 줄 텍스트 상자에 `NAME=VALUE` 형식의 항목을 추가합니다. 이 설정은 검색 경로 설정에 따라 `PYTHONPATH`가 설정된 후에 마지막으로 기존 전역 환경 변수의 맨 위에 적용되므로 다른 변수를 수동으로 재정의하는 데 사용될 수 있습니다. |

<a name="the-debug-interactive-window"></a>

## <a name="immediate-and-interactive-windows"></a>직접 실행 창 및 대화형 창

디버깅 세션 중에 사용할 수 있는 두 개의 대화형 창, 즉 표준 Visual Studio 직접 실행 창과 Python 대화형 디버그 창이 있습니다.

[직접 실행] 창(**디버그 > 창 > 직접 실행**)은 Python 식을 빠르게 계산하고 실행 중인 프로그램 내에서 변수를 검사하거나 할당하는 데 사용됩니다. 자세한 내용은 일반적인 [직접 실행 창](../ide/reference/immediate-window.md) 문서를 참조하세요.

Python 대화형 디버그 창(**디버그 > 창 > Python 대화형 디버그**)은 코드 작성 및 실행을 포함하여 디버깅 중에 완벽한 [대화형 REPL](python-interactive-repl-in-visual-studio.md) 환경을 사용할 수 있기 때문에 더욱 다양하게 구성되었습니다. **디버그 > 프로세스에 연결**를 통해 연결된 프로세스를 포함하여 표준 Python 시작 관리자를 사용하여 디버거에서 시작된 모든 프로세스에 자동으로 연결됩니다. 그러나 C/C++ 혼합 모드 디버깅을 사용하는 경우에는 사용할 수 없습니다.

![Python 대화형 디버그 창](media/debugging-interactive.png)

대화형 디버그 창은 [표준 REPL 명령](python-interactive-repl-in-visual-studio.md#meta-commands) 외에도 다음과 같은 특수 메타 명령을 지원합니다.

| 명령 | 인수 | 설명 |
| --- | --- | --- |
| `$continue`, `$cont`, `$c` | 현재 문에서 프로그램 실행을 시작합니다. |
| `$down`, `$d` | 스택 추적에서 현재 프레임을 한 수준 아래로 이동합니다. |
| `$frame` | | 현재 프레임 ID를 표시합니다.
| `$frame` | 프레임 ID | 현재 프레임을 지정된 프레임 ID로 전환합니다.
| `$load` | 파일에서 명령을 로드하고 완료될 때까지 실행합니다. |
| `$proc` |  | 현재 프로세스 ID를 표시합니다. |
| `$proc` | 프로세스 ID | 현재 프로세스를 지정된 프로세스 ID로 전환합니다. |
| `$procs` | | 현재 디버깅 중인 프로세스를 나열합니다. |
| `$stepin`, `$step`, `$s` | 가능한 경우 다음 함수 호출을 단계별로 실행합니다. |
| `$stepout`, `$return`, `$r` | 현재 함수에서 나갑니다. |
| `$stepover`, `$until`, `$unt` | 다음 함수 호출을 건너뜁니다. |
| `$thread` | | 현재 스레드 ID를 표시합니다. |
| `$thread` | 스레드 ID | 현재 스레드를 지정된 스레드 ID로 전환합니다. |
| `$threads` | | 현재 디버깅 중인 스레드를 나열합니다. |
| `$up`, `$u` | | 스택 추적에서 현재 프레임을 한 레벨 위로 이동합니다. |
| `$where`, `$w`, `$bt` | 현재 스레드의 프레임을 나열합니다. |

프로세스, 스레드 및 호출 스택과 같은 표준 디버거 창은 대화형 디버그 창과 동기화되지 않습니다. 대화형 디버그 창에서 활성 프로세스, 스레드 또는 프레임을 변경하는 경우 다른 디버거 창에는 적용되지 않습니다. 마찬가지로, 다른 디버거 창에서 활성 프로세스, 스레드 또는 프레임을 변경하는 경우 대화형 디버그 창에는 적용되지 않습니다.

대화형 디버그 창에는 **도구 > 옵션 > Python 도구 > 대화형 디버그 창**를 통해 액세스할 수 있는 고유한 옵션 집합이 있습니다. 각 Python 환경마다 별도의 인스턴스가 있는 일반 Python 대화형 창과 달리, 하나의 [대화형 디버그] 창만 있으며, 디버깅 중인 프로세스에 대해 항상 Python 인터프리터를 사용합니다. [옵션 - 디버깅 옵션](python-support-options-and-settings-in-visual-studio.md#debugging-options)을 참조하세요.

![대화형 디버그 창 옵션](media/debugging-interactive-options.png)

## <a name="see-also"></a>참고 항목

Visual Studio 디버거에 대한 자세한 내용은 [Visual Studio에서 디버깅](../debugger/debugger-feature-tour.md)을 참조하세요.