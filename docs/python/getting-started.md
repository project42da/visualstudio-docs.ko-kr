---
title: "Visual Studio에서 Python 사용 시작 | Microsoft Docs"
ms.custom: 
ms.date: 7/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: a9087b19-275b-4cc1-8d0c-f9c4356c9ce8
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: d0a5b44962b0cfbe549453b1760a38237de7e6ab
ms.openlocfilehash: 420af3d78a514a7e6b6ded186c204ad8301c4c85
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---

# <a name="getting-started-with-python-in-visual-studio"></a>Visual Studio에서 Python 시작

Python 작업에 Visual Studio(Visual Studio 2017)가 설치되어 있거나 Visual Studio(Visual Studio 2015 및 이전 버전)가 설치되어 있으면 Python 개발 환경을 살펴볼 수 있습니다. (필요한 경우 [설치](installation.md)를 참조하세요.)

이 연습에서는 빈 Python 응용 프로그램을 새로 만들고, 사용할 Python 환경을 선택하고, 몇 가지 코드를 작성하여 IntelliSense가 작동하는 모습을 확인하는 과정을 안내합니다. 그런 다음 대화형 REPL 창을 사용하여 짧은 시간에 더 많은 코드를 만든 다음 프로그램을 완료하고 자체적으로 실행하고 디버거에서 실행합니다.

> [!Note]
> 이 연습에서는 Visual Studio 2017에서 Python 환경을 살펴봅니다. 다른 버전도 유사하지만 세부적으로는 약간 다를 수 있습니다.

## <a name="create-a-new-python-project"></a>새 Python 프로젝트 만들기

Visual Studio의 Python 지원 기능에는 Azure 클라우드 서비스와 Bottle, Flask 및 Django 프레임워크를 사용하는 웹 응용 프로그램을 비롯한 다양한 유형의 프로젝트를 시작할 수 있는 많은 [프로젝트 템플릿](python-projects.md)이 포함되어 있습니다. 그러나 이 연습에서는 빈 프로젝트로 시작하겠습니다.

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하면 **새 프로젝트** 대화 상자가 표시됩니다. 여기서 템플릿을 찾아 선택하고, 프로젝트를 만들 폴더를 지정할 수 있습니다.

1. Python 템플릿은 왼쪽의 **템플릿 > 다른 언어 > Python**으로 이동하거나 “Python”을 검색하면 찾을 수 있습니다.

    ![Python 프로젝트가 표시된 새 프로젝트 대화 상자](media/getting-started-new-project.png)

1. "Python 응용 프로그램" 템플릿을 선택하고 프로젝트 폴더를 지정하고 **확인**을 선택합니다. (지금 바로 프로젝트의 로컬 리포지토리를 만들려는 경우 **소스 제어에 추가** 옵션도 선택하세요).

    > [!Tip]
    > "기존 Python 코드에서" 템플릿을 사용하면 빈 프로젝트를 새로 만들어 기존 코드를 가져오지 않고 Python 코드를 이미 포함하는 폴더에서 Visual Studio 프로젝트를 빠르게 만들 수 있습니다.

1. 몇 분 후에 Visual Studio 솔루션 탐색기 창에 프로젝트가 열립니다. 여기서 프로젝트의 파일 및 폴더를 찾아보고 환경을 관리할 수 있습니다.

    ![Python 프로젝트와 솔루션 탐색기](media/getting-started-solution-explorer-1.png)

1. **Python 환경** 노드를 확장하고 어떤 Python 인터프리터가 이 프로젝트의 현재 기본값인지 확인합니다. 또한 해당 인터프리터 노드를 확장하면 해당 환경에서 사용할 수 있는 라이브러리 목록이 표시됩니다.

    ![Python 환경을 보여 주는 솔루션 탐색기](media/getting-started-solution-explorer-2.png)

1. Visual Studio 2015 또는 이전 버전을 사용 중인 경우에는 기본적으로 설치된 Python 인터프리터가 없을 것입니다. 이 프로세스에 대한 자세한 내용은 [Python 인터프리터 선택 및 설치](python-environments.md#selecting-and-installing-python-interpreters)를 참조하세요.

### <a name="going-deeper"></a>자세히 알아보기

- [Visual Studio의 Python 프로젝트](python-projects.md).
- [웹 프로젝트 템플릿](template-web.md)
- [Django 웹 프로젝트 템플릿](template-django.md)
- [Azure 클라우드 서비스 템플릿](template-azure-cloud-service.md)

## <a name="writing-and-running-code"></a>코드 작성 및 실행

1. 새로운 "Python 응용 프로그램" 프로젝트를 만들면 Visual Studio 편집기에 `PythonApplication1.py`라는 기본 빈 파일이 열립니다. 이름을 변경하려면 솔루션 탐색기에서 파일을 마우스 오른쪽 단추로 클릭한 후 **이름 바꾸기**를 선택하고 `hello.py`로 이름을 변경합니다.

1. `print("Hello world")`를 입력하기 시작하면 Visual Studio IntelliSense가 입력 도중에 자동 완성 옵션을 어떻게 표시하는지 알 수 있습니다. 드롭다운 목록에서 윤곽선이 있는 옵션은 Tab 키를 누르면 사용되는 기본 완성입니다. 완성 기능은 더 긴 문이나 식별자가 포함된 경우에 가장 유용합니다.

    ![IntelliSense 자동 완성 팝업](media/getting-started-coding-1.png)

1. IntelliSense는 사용자가 사용하는 문, 호출하는 함수 등에 따라 다른 정보를 표시합니다. `print` 함수는 `(`를 입력하여 호출하면 함수 사용법에 대한 전체 정보를 팝업 창에 표시하고, 사용자가 입력해야 하는 현재 인수를 굵게 표시합니다(여기에 표시된 **value**).

    ![IntelliSense 함수 자동 완성 팝업](media/getting-started-coding-2.png)

1. 다음과 일치하도록 문을 완성하세요.

  ```python
  print("Hello world")
  ```

1. 코드를 실행하려면 F5 키를 누르거나 **디버그 > 디버깅 시작** 메뉴 항목을 선택합니다.

    > [!Note]
    > Visual Studio 2015 및 이전 버전에서 인터프리터가 없다는 메시지가 표시될 경우 기본적으로 인터프리터가 설치되어 있지 않은 것이므로 [Python 인터프리터 선택 및 설치](python-environments.md#selecting-and-installing-python-interpreters)를 참조하세요.

1. Visual Studio에서 프로젝트의 기본 환경을 사용하여 코드를 실행하고 명령 창에 결과를 표시합니다. 키를 눌러 해당 창을 닫고 디버깅 세션을 종료합니다.

    ![디버그 도구 모음의 시작 단추](media/getting-started-coding-4.png)

1. IntelliSense는 문과 함수 외에 `import` 문 완성 기능도 제공합니다. 가져오기 완성 기능을 사용하면 사용자 환경에서 사용할 수 있는 모듈과 해당 모듈에서 사용할 수 있는 멤버를 손쉽게 확인할 수 있습니다. 편집기에서 `print` 줄을 삭제하고 `import` 입력을 시작합니다. 모듈 목록이 표시됩니다.

    ![import 문에 사용할 수 있는 모듈을 보여 주는 IntellSense](media/getting-started-coding-5.png)

1. `sys`를 입력하거나 선택하여 줄을 완성합니다.

1. 다음 줄에 `from`을 입력하면 모듈 목록을 다시 볼 수 있습니다.

    ![from 문에 사용할 수 있는 모듈을 보여 주는 IntellSense](media/getting-started-coding-6.png)

1. `math`를 선택하거나 입력한 후 계속해서 공백과 `import`를 입력하면 모듈 멤버가 표시됩니다.

    ![모듈 멤버를 보여 주는 IntellSense](media/getting-started-coding-7.png)

1. `sin`, `cos` 및 `radians` 멤버를 가져오고 각각에 사용 가능한 자동 완성을 확인하여 완료합니다. 완료되면 코드가 다음과 같이 표시됩니다.

  ```python
  import sys  
  from math import sin, cos, radians          
  ```

> [!Tip]
> 완성 기능은 사용자가 입력하는 하위 문자열, 단어와 일치하는 부분, 단어 시작 부분의 글자, 생략된 문자에 작동합니다. 자세한 내용은 [코드 편집 - 완성](code-editing.md#completions)을 참조하세요.

다음 단계에서는 대화형 REPL 창에서 디버거를 실행하지 않고 즉시 테스트할 수 있는 몇 가지 코드를 작성해 보겠습니다.

### <a name="going-deeper"></a>자세히 알아보기

- [코드 편집](code-editing.md)
- [코드 서식 지정](code-formatting.md)
- [코드 리팩터링](code-refactoring.md)
- [PyLint 사용](code-pylint.md)


## <a name="using-the-interactive-repl-window"></a>대화형 REPL 창 사용

Python용 Visual Studio 대화형 창은 일반적인 편집-빌드-디버그 주기를 크게 단축하는 풍부한 REPL(읽기-평가-인쇄-루프) 경험을 제공합니다. Python 명령줄의 REPL 환경과 유사하지만 여기서 보여 주는 몇 가지 추가 기능을 제공합니다.

1. Visual Studio 주 메뉴에서 **보기 > 다른 창 > Python 대화형 창**을 선택하여 대화형 창을 엽니다. 이 창은 일반적인 >>> Python REPL 프롬프트와 함께 열립니다. 툴바의 드롭다운 메뉴를 사용하여 언제든지 환경을 변경할 수 있습니다.

    ![Python 대화형 창](media/getting-started-interactive-1.png)

1. 몇 가지 문(예: `print("hello")`) 및 식(예: `123/567`)을 입력하여 즉각적인 결과를 확인하세요.

    ![Python 대화형 창의 즉각적인 결과](media/getting-started-interactive-2.png)

1. 함수 정의와 같이 여러 줄로 된 문을 작성하기 시작하면 대화형 창에 명령줄 REPL과 달리 연속되는 줄을 위해 자동 들여쓰기를 제공하는 ... 프롬프트가 표시됩니다.

    ![연속 문을 지원하는 Python 대화형 창](media/getting-started-interactive-3.png)

1. 대화형 창에서는 사용자가 입력한 모든 내용의 전체 기록을 제공하고 여러 줄 기록 항목으로 명령줄 REPL을 개선합니다. 예를 들어 함수 줄을 줄별로 다시 만들지 않고 위에서 설명한 `f` 함수의 전체 정의를 단일 단위로 손쉽게 회수하고 이름을 손쉽게 `make_double`로 변경할 수 있습니다.

1. 또 다른 유용한 기능은 디버거에서 실행할 다른 코드를 작성하지 않고 편집기 창에서 대화형 창으로 여러 줄의 코드를 신속하게 전송하여 신속한 REPL 환경에서 작업하는 기능이 있습니다. 기능을 확인하려면 먼저 편집기에 열려 있는 hello.py 파일에 다음 코드를 추가하세요.

  ```python
  def make_dot_string(x):  
      return ' ' * int(10 * cos(radians(x)) + 10) + 'o'
  ```

1. hello.py의 모든 코드(`import` 문 포함)를 선택하고 마우스 오른쪽 단추를 클릭한 후 **Interactive로 보내기**(Ctrl+Enter)를 선택합니다. 시스템에서 코드를 대화형 창에 즉시 붙여 넣고 실행합니다. 코드는 함수를 정의하므로 해당 함수를 여러 번 호출하여 신속하게 테스트할 수 있습니다.

    ![대화형 창에 코드 보내기](media/getting-started-interactive-4.png)

1. 편집기에서 한 줄에 캐럿을 놓고 Ctrl+Enter를 사용하는 것도 코드를 단계별로 실행하는 편리한 방법입니다. Ctrl+Enter를 누르면 대화형 창에서 현재 줄이 실행되고 다음 줄에 캐럿이 자동으로 설정됩니다. Ctrl+Enter를 반복해서 누르면 파일에 있는 모든 코드를 실행할 수 있습니다.

1. Visual Studio 2017에서는 대화형 창에 여러 줄을 직접 붙여넣을 수 있습니다(이전 버전에서는 해당 줄을 편집기 창에 붙여넣고 선택한 다음 **Interactive로 보내기**를 사용해야 함). 붙여넣으면 다음에서 볼 수 있듯이 대화형 창에서 해당 코드가 실행됩니다.

  ```python
  for i in range(360):
      s = make_dot_string(i)  
      print(s) 
  ```

    ![Interactive로 보내기를 사용하여 여러 줄의 코드 붙여넣기](media/getting-started-interactive-5.png)

1. 함수 정의는 REPL 기록에 단일 단위로 존재하기 때문에 손쉽게 다시 돌아가서 원하는 부분을 변경한 후 함수를 다시 테스트할 수 있습니다.

1. 대화형 창에서 작성한 코드에 만족할 경우 해당 코드를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **코드 복사**를 선택하고 편집기에 붙여넣을 수 있습니다. 이 **코드 복사** 명령은 모든 출력과 >>> 및 ... 프롬프트 텍스트를 자동으로 생략합니다. 예를 들어 아래에 표시된 선택 영역에 이 명령을 사용하는 경우:

  ![대화형 창 코드 복사 명령](media/getting-started-interactive-6.png)

  다음에만 붙여넣습니다.

  ```python
  make_dot_string(180)
  make_dot_string(135)
  for i in range(360):
      s = make_dot_string(i)  
      print(s) 
  ```

1. 마지막으로, 대화형 창은 파일을 로드하고, 기록 손실 없이 환경을 다시 설정하고, 도중에 주석을 삽입하기 위한 많은 메타 명령을 제공합니다. 자세한 내용은 [대화형 창 - 메타 명령](interactive-repl.md#meta-commands)을 참조하세요.

### <a name="going-deeper"></a>자세히 알아보기

- [대화형 창 사용](interactive-repl.md)
- [IPython REPL 사용](interactive-repl-ipython.md)

## <a name="running-code-in-the-debugger"></a>디버거에서 코드 실행

Visual Studio는 프로젝트 관리, 풍부한 편집 환경 제공 및 대화형 창 외에 Python 코드에 대한 완전한 기능의 디버깅 지원을 제공합니다.

1. 다음과 일치하도록 hello.py 파일의 코드를 편집하세요.

  ```python  
  from math import sin, cos, radians  
  import sys  
    
  def make_dot_string(x):  
      return ' ' * int(10 * cos(radians(x)) + 10) + 'o'  
    
  def main():  
      for i in range(360 * 5):
          s = make_dot_string(i)  
          print(s)  
            
  main()
  ```  

1. F5 키를 누르거나 **디버그 > 디버깅 시작** 메뉴 명령을 선택하여 코드가 제대로 작동하는지 확인합니다. 이 명령은 디버거에서 코드를 실행하지만 중단점이 설정되어 있지 않으므로 몇 가지 반복에 대해 웨이브 패턴만 출력합니다. 이때 아무 키나 누르면 출력 창이 닫힙니다.

    > [!Tip]
    > 프로그램이 완료되었을 때 출력 창을 자동으로 닫으려면 `main()` 호출을 다음 코드로 바꾸세요.
    >
    > ```python    
    > if __name__ == "__main__":  
    >     sys.exit(int(main() or 0))      
    > ```
    > 
    > 또는 원하지 않을 때 출력 창이 자동으로 닫히는 경우가 발생하면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**, **디버그** 탭을 차례로 선택한 다음 **인터프리터 인수** 필드에 `-i`를 추가합니다. 이 인수를 사용하면 프로그램이 완료된 후 인터프리터가 대화형 모드로 전환되어 창이 열린 상태로 유지되며 Ctrl+Z, Enter 키를 누르면 종료됩니다.

1. `main` 함수의 첫 번째 줄 옆에 있는 왼쪽 회색 여백을 클릭하거나 해당 줄에 캐럿을 추가하고 **디버그 > 중단점 설정/해제** 명령(F9)을 사용하여 해당 줄에 중단점을 설정합니다. 회색 여백에 (아래에 파란색 화살표로 표시된) 중단점을 나타내는 빨간색 점이 표시됩니다.

    ![중단점 설정](media/getting-started-debugging-1.png)

1. 디버거를 다시 시작하고 해당 중단점이 있는 줄에서 코드 실행이 중지되는 것을 확인합니다. 여기서 호출 스택을 보고 지역 창의 지역 변수를 검사할 수 있습니다.

    ![Python의 중단점 UI 환경](media/getting-started-debugging-2.png)

1. F10 키, **디버그 > 프로시저 단위 실행** 명령 또는 프로시저 단위 실행 툴바 단추를 사용하여 `for` 루프의 몇 가지 반복을 한 줄씩 단계별로 실행합니다. 프로시저 단위 실행은 디버거가 `make_dot_string`에 대한 각 호출을 실행하지만 해당 함수 내에서 중단되지 않음을 의미합니다(중단점을 설정하지 않은 경우).

1. 도구 모음에 표시되는 단계별 실행 단추 세 개(아래에 표시)는 왼쪽부터 오른쪽의 순서로 한 단계씩 코드 실행, 프로시저 단위 실행, 프로시저 나가기입니다.

    ![단계별 실행 툴바 단추](media/getting-started-debugging-3.png)

1. 한 단계씩 코드 실행(F11)을 사용하면 `make_dot_string`이 한 단계씩 실행됩니다. `for` 루프에서 해당 함수로 한 단계씩 실행되는 것을 확인합니다. 다시 단계별로 실행하면 `for` 루프로 돌아가지만 함수에 추가 줄이 있다면 하나씩 단계별로 실행하는 것이 좋습니다. 함수 내에 나머지 함수 줄을 실행한 후 호출 코드로 돌아가려면 프로시저 나가기(Shift+F11)를 사용합니다.

1. 다음 중단점에 도달할 때까지 (또는 프로그램이 종료될 때까지) 코드를 계속 실행하려면 F5 키를 다시 누르거나 **계속** 툴바 단추 또는 **디버그 > 계속**을 선택합니다. `for` 루프에 중단점이 있기 때문에 다음 반복에서 중단됩니다.

1. 수백 개의 루프 반복을 단계별로 실행하는 작업은 지루할 수 있으므로 이전에 설정된 중단점에 조건을 추가하여 `i` 값이 특정 값(예: 1600)을 초과할 경우에만 중단되도록 할 수 있습니다. 조건을 설정하려면 빨간색 중단점을 마우스 오른쪽 단추로 클릭하고 **조건...**을 선택합니다. 표시되는 중단점 설정 창에서 `i > 1600`을 식으로 입력하고 **닫기**를 선택합니다. 이제 F5 키를 눌러 계속하고 프로그램이 잠시 실행된 후 다시 중단되는 것을 확인합니다. 

    ![중단점 조건 설정](media/getting-started-debugging-4.png)

1. 프로그램을 완료하려면 중단점을 다시 설정/해제하고 F5 키를 누르면 됩니다. 디버깅이 완료되면 Visual Studio가 편집 모드로 돌아갑니다.

### <a name="going-deeper"></a>자세히 알아보기

- [디버깅](debugging.md).
- Visual Studio의 디버깅 기능에 대한 자세한 설명서를 보려면 [Visual Studio에서 디버깅](../debugger/debugging-in-visual-studio.md)도 참조하세요.

## <a name="next-steps"></a>다음 단계

앞에 나온 "자세히 알아보기" 링크 외에 Visual Studio의 Python 환경에 제공되는 추가 기능을 다루는 항목은 다음과 같습니다.

- Visual Studio가 Azure 앱 서비스에 연결하는 방법을 보려면 [Azure에 Python 웹 응용 프로그램 게시](publishing-to-azure.md)를 참조하세요.
- 가상 환경을 포함한 여러 환경을 전역적으로, 그리고 개별 프로젝트별로 관리하는 방법을 살펴보려면 [Python 환경](python-environments.md)을 참조하세요.
- Visual Studio는 [플랫폼 간 원격 디버깅](debugging-cross-platform-remote.md) 및 [Azure 원격 디버깅](debugging-azure-remote.md)에 설명된 것처럼 원격 서버에서 응용 프로그램을 디버깅하는 기능을 제공합니다.
- [Visual Studio 프로파일링](profiling.md)을 사용하여 Python 코드의 성능을 평가할 수 있습니다.
- Python으로 작성된 단위 테스트는 [단위 테스트](unit-testing.md)에 설명된 것처럼 Visual Studio 테스트 탐색기와 직접 통합됩니다.
- [Microsoft Virtual Academy의 무료 Python 코스](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Microsoft Virtual Academy의 상위 Python 질문](https://aka.ms/mva-top-python-questions)

