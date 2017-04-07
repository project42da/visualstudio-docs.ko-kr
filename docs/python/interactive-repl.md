---
title: "Visual Studio의 Python 대화형 REPL | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 642dc47e-c265-44ea-a77d-3db14170a36f
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 7d726441c2d6953bd7b50451bec7fff05d5d71b0
ms.openlocfilehash: f31d92f193af3fb32f61030ca52e444ae2baa60b
ms.lasthandoff: 03/10/2017

---

# <a name="working-with-the-python-interactive-window"></a>Python 대화형 창 사용

Visual Studio는 각 Python 환경에 대화형 읽기-평가-인쇄 루프(REPL) 창을 제공하여 명령줄에서 `python.exe`와 관련한 REPL을 개선합니다. 대화형 창(**보기 > 다른 창 > &lt;환경&gt; 대화형** 창 메뉴 명령으로 열 수 있음)을 사용하면 임의의 Python 코드를 입력하고 즉각적인 결과를 확인할 수 있어 API와 관련된 내용을 배우고 실험하는 데 도움이 되고, 프로젝트에 포함할 작업 코드를 대화형으로 개발할 수 있습니다.

![Python 대화형 창](media/interactive-window.png)

Visual Studio에는 선택 가능한 다양한 Python REPL 모드가 있습니다.

| REPL | 설명 | 편집 | 디버깅 | 이미지 |
| --- | --- | --- | --- | --- |
| 표준 | 기본 REPL, Python에 직접 명령 | 표준 편집(여러 줄 등). | 예, `$attach`를 통해 | 아니요 |
| 디버그 | 기본 REPL, 디버깅된 Python 프로세스에 명령 | 표준 편집 | 디버깅만 | 아니요 |
| IPython | REPL이 IPython 백 엔드에 명령 | IPython 명령, Pylab의 편리한 기능 | 아니요 | 예, REPL에서 인라인으로 |
| Pylab가 없는 IPython | REPL이 IPython 백 엔드에 명령 | 표준 IPython | 아니요 | 예, 별도의 창 | 

이 항목에서는 **표준** 및 **디버그** REPL 모드를 설명합니다. IPython 모드에 대한 자세한 내용은 [IPython REPL 사용](interactive-repl-ipython.md)을 참조하세요.

Python 대화형 창에 대한 소개는 [Visual Studio에서 Python 시작, 5부: 대화형 REPL](https://youtu.be/yc2CROtTsC0?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)(youtube.com, 2분 51초)을 참조하세요.

> [!VIDEO https://www.youtube.com/embed/yc2CROtTsC0]

## <a name="opening-an-interactive-window"></a>대화형 창 열기

특정 환경에서 대화형 창을 여는 방법은 여러 가지가 있습니다.

첫째, Python 환경 창(**보기 > 다른 창 > Python 환경** 또는 Ctrl+K, Ctrl+`)으로 전환하고 선택한 환경에서 **대화형 창 열기** 명령 또는 단추를 선택합니다.

![Python 환경 창의 대화형 창 링크](media/interactive-window-opening.png)

둘째, **보기 > 다른 창**에는 각 사용자 환경에 대한 **대화형** 명령이 있으며, 일반적으로 메뉴의 아래쪽 근처에 표시됩니다.

![보기 > 다른 창의 대화형 창 메뉴 항목](media/interactive-window-menu.png)

셋째, **디버그 > Python 대화형 창에서 [프로젝트 | 파일] 실행** 메뉴 명령(Shift+Alt+F5)을 선택하여 프로젝트의 시작 파일 또는 독립 실행형 파일에서 대화형 창을 열 수 있습니다.

![Python 대화형 창에서 프로젝트 실행 메뉴](media/interactive-execute-project.png)

마지막으로, 파일의 코드를 선택하고 아래에 설명된 [대화형 명령으로 코드 보내기](#send-code-to-interactive) 명령을 사용할 수 있습니다.

## <a name="interactive-window-options"></a>대화형 창 옵션

Python 환경 창의 **대화형 창 구성** 또는 **도구 > 옵션 > Python 도구 > 대화형 창**을 통해 대화형 창의 다양한 측면을 제어할 수 있습니다.

![Python 대화형 창 옵션](media/interactive-window-options.png)

또한 디버깅 세션 중에 사용 시 동작을 제어하는 **디버그 대화형 창**을 위한 별도의 옵션 집합도 있습니다.

![Python 대화형 창 디버그 옵션](media/interactive-window-debug-options.png)

## <a name="using-the-interactive-window"></a>대화형 창 사용

대화형 창이 열리면 `>>>` 프롬프트에서 코드를 한 줄씩 입력하기 시작할 수 있습니다. 대화형 창은 사용자가 각 줄을 입력할 때 해당 줄을 실행합니다. 여기에는 모듈을 가져오고 변수를 정의하는 등의 과정이 포함됩니다. 아래 그림에 표시된 처음 두 줄에서 이를 확인할 수 있습니다.

![Python 대화형 창](media/interactive-window.png)

`for` 문처럼 문이 콜론으로 끝나는 경우는 예외입니다. 대화형 창은 추가적인 코드 줄이 있어야 코드 블록을 제대로 실행할 수 있다는 것을 알고 있기 때문입니다. 이 경우 위의 그림에서 네 번째 및 다섯 번째 줄에 표시된 것처럼 줄 프롬프트가 `...`로 바뀌는데, 블록에 추가 줄을 입력해야 한다는 의미입니다. 빈 줄에서 Enter 키를 누르면 대화형 창이 블록을 닫고 인터프리터에서 실행합니다.

> [!Tip]
> 대화형 창은 주변 범위에 속하는 문을 자동으로 들여쓰기하여 일반적인 명령줄 REPL 환경을 개선합니다. 또한 명령줄 REPL은 단일 줄만 제공하지만 대화형 창은 위쪽 화살표로 회수할 수 있는 기록에 여러 줄 항목을 제공합니다.

대화형 창은 새 라이브러리를 사용해볼 수 있는 좋은 방법입니다. 라이브러리를 가져오고 하위 패키지, 클래스 및 함수를 검사할 수 있습니다.  Python은 `help()` 함수를 통해 이 모든 정보를 전달할 수 있습니다.  또한 Visual Studio의 Python 지원은 라이브러리를 실행하지 않고도 편집기에서 사용된 코드 모델링에 따라 제안 및 설명서를 제공합니다.  코드를 실행할 때 Visual Studio는 Python 런타임의 정보를 사용하여 이러한 제안을 향상시킵니다.  

<a name="meta-commands"></a> 대화형 창은 몇 가지 메타 명령도 지원합니다. 모든 메타 명령은 `$`로 시작하고, `$help`를 입력하면 메타 명령의 목록을 가져올 수 있고, `$help <command>`를 입력하면 특정 명령의 자세한 사용법을 가져올 수 있습니다.

| 메타 명령 | 설명 |
| --- | --- |
| `$$` | 세션 전체에서 코드에 주석을 추가하는 데 도움이 되는 메모를 삽입합니다. |
| `$attach` | REPL 창 프로세스에 Visual Studio 디버거를 첨부하여 디버깅을 활성화합니다. |
| `$cls`, `$clear` | 편집기 창의 내용을 지워서 기록 및 실행 컨텍스트를 그대로 유지합니다. |
| `$help` | 명령 목록 또는 특정 명령에 대한 도움말을 표시합니다. |
| `$load` | 파일에서 명령을 로드하고 완료될 때까지 실행합니다. |
| `$mod` | 현재 범위를 지정된 모듈 이름으로 전환합니다. |
| `$reset` | 실행 환경을 초기 상태로 다시 설정하되, 기록을 유지합니다. |
| `$wait` | 지정된 기간(밀리초) 이상으로 기다립니다. |

MEF(.NET용 Managed Extensibility Framework)를 통해 명령을 확장할 수도 있습니다.

## <a name="switching-scopes"></a>범위 전환

기본적으로 프로젝트의 대화형 창은 명령 프롬프트에서 실행한 것처럼 프로젝트의 시작 파일로 범위가 지정됩니다. 독립 실행형 파일의 경우 해당 파일로 범위가 지정됩니다. 그러나 REPL 세션 중에 언제든지 대화형 창 맨 위에 있는 드롭다운 메뉴를 사용하여 범위를 변경할 수 있습니다.

![대화형 창 범위](media/interactive-scopes.png)

`import os`를 입력하는 등의 방법으로 모듈을 가져오면 드롭다운에 해당 모듈의 모든 범위로 전환하는 옵션이 표시됩니다. 또한 대화형 창에 새 범위를 나타내는 메시지도 표시되므로 세션 중에 특정 상대에 도달하는 방법을 추적할 수 있습니다.

범위에 `dir()`을 입력하면 함수 이름, 클래스 및 변수 등 해당 범위에서 유효한 식별자가 표시됩니다. 예를 들어 `$mod importlib` 뒤에 `dir()`을 사용하면 다음이 표시됩니다.

![importlib 범위의 대화형 창](media/interactive-importlib-scope.png)

<a name="sending-code-to-interactive"</a>
## <a name="send-code-to-interactive-command"></a>대화형 명령으로 코드 보내기

대화형 창 내에서 직접 작업할 수 있을 뿐만 아니라 편집기에서 코드를 선택하고 마우스 오른쪽 단추를 클릭하고 **Interactive로 보내기**를 선택할 수 있습니다.

![Interactive로 보내기 메뉴 명령](media/interactive-send-to.png)

코드 개발 중 테스트를 포함하여 반복적이거나 발전적인 코드 개발에 유용합니다. 예를 들어 대화형 창에 코드 조각을 보내고 출력을 확인한 후 위쪽 화살표를 눌러 코드를 다시 표시하고 수정하고 Ctrl+Enter를 눌러 빠르게 테스트할 수 있습니다. (입력의 끝에서 Enter 키를 누르면 코드가 실행되지만 입력 중에 Enter 키를 누르면 줄 바꿈이 삽입됩니다.) 원하는 코드를 만들었으면 프로젝트 파일에 다시 쉽게 복사할 수 있습니다.

또한 코드를 선택하고 마우스 오른쪽 단추를 클릭한 후 **모듈 정의로 보내기**를 선택할 수도 있습니다. 그러면 시스템에서 대화형 프로세스를 검색하여 편집 중인 현재 파일과 일치하는 모듈을 찾습니다. 올바른 모듈이 발견되면 `$mod` 메타 명령을 사용하여 해당 모듈로 전환하고(해당 모듈은 대화형 창 세션 기록의 일부가 됨), 선택 영역을 평가하기 위해 대화형 창에 붙여 넣습니다. 이는 편집기에서 코드를 복사하고 대화형 창에서 범위를 전환하고 수동으로 붙여 넣는 프로세스를 단축합니다.

## <a name="intellisense-behavior"></a>IntelliSense 동작

IntelliSense가 소스 코드 분석만을 기반으로 하는 코드 편집기와 달리 대화형 창에는 라이브 개체에 기반을 둔 IntelliSense가 포함되어 있습니다. 따라서 동적으로 생성된 코드의 경우 특히 대화형 창의 제안이 더 정확합니다. 단점은 부작용(예: 로깅 메시지)이 있는 함수가 개발 환경에 영향을 줄 수 있다는 점입니다.

이 부분이 문제가 될 경우 **완료 모드** 그룹의 **도구 > 옵션 > Python 도구 > 대화형 창** 아래에서 설정을 변경하세요.

- **식을 계산하지 않음**: 제안에 일반적인 IntelliSense 엔진이 사용됩니다.
- **호출을 포함하는 식을 계산하지 않음**(기본값): `a.b`와 같은 단순 식은 계산하되 `a().b` 같은 호출을 포함하는 식은 일반 엔진을 사용합니다.
- **항상 식을 계산함**: 부작용이 있더라도 상관없이 전체 식을 실행하여 제안을 가져옵니다.
