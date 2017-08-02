---
title: "Visual Studio에서 Python 환경 | Microsoft Docs"
ms.custom: 
ms.date: 5/8/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8876f8c1-4770-44dc-97d8-bf0035ae8196
caps.latest.revision: 11
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: 9140ca7549eefc3ac221f3ca0aa54fde482c8623
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---

# <a name="python-environments"></a>Python 환경

Visual Studio에서 Python을 통해 여러 Python 환경을 간편하게 관리하고 다양한 프로젝트에 대해 쉽게 전환할 수 있습니다. 

참고: Visual Studio에서 Python을 처음 사용하는 경우 현재 이 토론의 근간이 되는 다음 항목을 먼저 참조하세요.

- [Visual Studio에서 Python 작업](python-in-visual-studio.md)
- [Visual Studio에서 Python 지원 설치](installation.md)

항상 Python 코드를 실행하는 Python *환경*은 인터프리터, 라이브러리(일반적으로 Python 표준 라이브러리) 및 설치된 패키지 집합으로 구성됩니다. 이러한 모든 요소에 따라, 어떤 언어로 구성되고 구문이 유효한지, 어떤 운영 체제 기능에 액세스할 수 있으며 어떤 패키지를 사용할 수 있는지가 결정됩니다.

또한 Visual Studio 환경에는 환경의 라이브러리에 대한 IntelliSense 데이터베이스가 포함되어 있으므로 Visual Studio 편집기에서 `import`와 같은 문을 입력하면 해당 라이브러리 내의 모듈과 사용 가능한 라이브러리 목록이 자동으로 표시됩니다.

개발자는 하나의 글로벌 Python 환경만 사용하지만 그 외 사용자는 이 항목에서 설명한 대로 여러 글로벌 환경, 프로젝트별 환경 및 가상 환경도 관리해야 하는 경우가 많습니다.

- [Python 인터프리터 선택 및 설치](#selecting-and-installing-python-interpreters)
- [Visual Studio에서 Python 환경 관리](#managing-python-environments-in-visual-studio)
- [글로벌 환경](#global-environments)
- [프로젝트별 환경](#project-specific-environments)
- [가상 환경](#virtual-environments)
- [필수 패키지 관리](#managing-required-packages)
- [검색 경로](#search-paths)

동영상 소개는 [자세히 알아보기: Python 인터프리터](https://youtu.be/KY1GEOo3qy0)(영문)(youtube.com, 13분 27초)를 참조하세요.

> [!VIDEO https://www.youtube.com/embed/KY1GEOo3qy0]

## <a name="selecting-and-installing-python-interpreters"></a>Python 인터프리터 선택 및 설치

Visual Studio 2017을 제외하고, Python 지원에는 Python 인터프리터가 함께 제공되지 않으므로 코드를 실행하려면 다음 중 하나를 설치해야 합니다. 일반적으로 Visual Studio는 새로 설치된 인터프리터를 자동으로 검색하고 이에 대한 환경을 설정합니다. 그렇지 않은 경우 아래 [기존 인터프리터에 대한 환경 만들기](#creating-an-environment-for-an-existing-interpreter)를 참조하세요.

| 인터프리터 | 설명 | 
| --- | --- | 
| [CPython](https://www.python.org/) | "기본"의 가장 널릴 사용되는 인터프리터로 32비트 및 64비트 버전으로 사용 가능합니다(32비트 권장). 최신 언어 기능, 최대 Python 패키지 호환성, 완전한 디버깅 지원 및 [IPython](http://ipython.org/)과 상호 interop을 포함합니다. 참고 항목: [Python 2 또는 Python 3을 사용해야 하나요?](http://wiki.python.org/moin/Python2orPython3) |
| [IronPython](http://ironpython.codeplex.com/) | Python의 .NET 구현으로, 32비트 및 64비트 버전으로 사용 가능하며 C#/F#/Visual Basic interop, .NET API에 대한 액세스, 표준 Python 디버깅(그러나 C++ 혼합 모드 디버깅은 제외) 및 혼합 IronPython/C# 디버깅을 제공합니다. 하지만 IronPython에서는 가상 환경을 지원하지 않습니다. | 
| [Anaconda](https://www.continuum.io) | Python에서 제공하는 개방형 데이터 과학 플랫폼으로, 최신 버전의 CPython과 설치하기 어려운 대부분의 패키지를 포함합니다. 달리 결정할 수 없는 경우 권장됩니다. |
| [PyPy](http://www.pypy.org/) | Python의 고성능 추적 JIT 구현으로, 장기적으로 실행되는 프로그램과 성능 문제를 확인했으나 다른 해결 방법을 찾을 수 없는 상황에 적절합니다. Visual Studio에서 작동하지만 고급 디버깅 기능은 제한적으로 지원됩니다. |
| [Jython](http://www.jython.org/) | JVM(Java Virtual Machine)에서 Python 구현. IronPython과 마찬가지로, Jython에서 실행되는 코드는 Java 클래스 및 라이브러리와 상호 작용할 수 있지만 CPython용으로 작성된 많은 라이브러리는 사용할 수 없습니다. Visual Studio에서 작동하지만 고급 디버깅 기능은 제한적으로 지원됩니다. |

Python 환경에 대한 새로운 검색 양식을 제공하려는 개발자인 경우 [PTVS 환경 검색](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments)(github.com)을 참조하세요.

## <a name="managing-python-environments-in-visual-studio"></a>Visual Studio에서 Python 환경 관리

Python 환경 창을 열려면 다음 중 하나를 수행합니다.

1. **보기> Other Windows(다른 창) > Python 환경** 메뉴 명령을 선택합니다.
1. 솔루션 탐색기에서 **Python 환경**을 마우스 오른쪽 단추로 클릭하고 **View All Python Environments(모든 Python 환경 보기)**를 선택합니다.

    ![솔루션 탐색기에서 모든 환경 명령 보기](~/python/media/environments-view-all.png)
    
두 경우 모두 Python 환경 창은 솔루션 탐색기의 형제 탭으로 나타납니다.

![Python 환경 창](~/python/media/environments-default-view.png)

위의 예에는 Python 3.4(32비트 CPython)가 IronPython 2.7 32비트 및 64비트 버전과 함께 설치되어 있습니다. 이 경우 굵게 표시된 기본 환경은 Python 3.4이며 모든 새로운 프로젝트에 사용됩니다. 목록에 환경이 표시되지 않는 경우 Visual Studio 2015 또는 이전 버전에 Visual Studio용 Python 도구를 설치했으나 Python 인터프리터를 설치하지 않은 것입니다(위의 [Python 인터프리터 선택 및 설치](#selecting-and-installing-python-interpreters) 참조). 

> [!Tip]
> 위에 표시된 것처럼 **Python 환경* 창이 좁으면 환경이 맨 위에 나열되고 아래에 다양한 탭이 표시됩니다. 하지만 창을 충분히 확장하면 넓은 보기가 표시되어 작업하기가 더 편리할 수 있습니다.
>
> ![Python 환경 창 확장된 보기](~/python/media/environments-expanded-view.png)

> [!Note]
> Visual Studio에서는 system-site-packages 옵션을 적용하지만 Visual Studio 내에 이를 변경하는 방법은 제공하지 않습니다.

### <a name="creating-an-environment-for-an-existing-interpreter"></a>기존 인터프리터에 대한 환경 만들기

일반적으로 Visual Studio는 레지스트리를 검사하여 설치된 Python 인터프리터를 찾지만 인터프리터가 비표준 방식으로 설치된 경우에는 찾을 수 없습니다. 이 경우 다음과 같이 Visual Studio에서 인터프리터를 직접 가리키도록 할 수 있습니다.

1. 환경 창에서 **+ 사용자 지정...**을 선택하면 새 환경이 생성되고 아래 설명된 [**구성** 탭](#configure-tab)이 열립니다.

    ![새 사용자 지정 환경의 기본 보기](~/python/media/environments-custom-1.png)

1. **설명** 필드에 환경에 대한 이름을 입력합니다.
1. **접두사 경로** 필드에 인터프리터의 경로를 입력하거나 찾습니다.
1. **자동 검색**을 선택하여 Visual Studio에서 나머지 필드를 완성하도록 하거나 수동으로 작성합니다.
1. **적용**을 선택하여 환경을 저장합니다.
1. 환경을 제거해야 하는 경우 **구성** 탭에서 **제거** 명령을 선택합니다.

### <a name="overview-tab"></a>개요 탭

기본값으로 설정, 해당 환경에서 [대화형(REPL) Windows](interactive-repl.md) 열기, 대화 상자로 이동하여 대화형 Windows 구성(**도구 > 옵션** 메뉴 명령, **Python 도구 > 대화형 Windows** 및 환경 이름 선택과 동일)과 같은 환경에 대한 기본 정보 및 명령을 제공합니다.

![Python 환경 개요 탭](~/python/media/environments-overview-tab.png)

> [!Note]
> 활성 환경을 변경하면 IntelliSense 데이터베이스가 로드되는 동안 Visual Studio가 잠시 응답하지 않을 수 있습니다. 많은 패키지가 있는 환경에서는 더 오랫동안 응답하지 않을 수 있습니다.

### <a name="configure-tab"></a>구성 탭

표시된 경우, 아래 표에 설명된 세부 정보를 포함합니다. 이 탭이 없는 경우 Visual Studio에서 모든 세부 정보를 자동으로 관리하는 것입니다.

![Python 환경 구성 탭](~/python/media/environments-configure-tab.png)

| 필드 | 설명 |
| --- | --- |
| **설명** | 환경에 지정할 이름입니다. |
| **접두사 경로** | 인터프리터의 기본 폴더 위치입니다. 이 부분을 입력하고 **자동 검색**을 클릭하면 Visual Studio에서 다른 필드를 채우려고 시도합니다. |
| **인터프리터 경로** | 인터프리터 실행 파일의 경로이며, 일반적으로 접두사 경로 다음에 `python.exe`가 나옵니다. |
| **창 인터프리터** | 비콘솔 실행 파일의 경로이며, 보통 접두사 경로 다음에 `pythonw.exe`가 나옵니다. |
| **라이브러리 경로** | 표준 라이브러리의 루트를 지정하지만 Visual Studio에서 인터프리터로부터 더 정확한 경로를 요청할 수 있는 경우 이 값은 무시될 수 있습니다. |
| **언어 버전** | 드롭다운 메뉴에서 선택합니다. |
| **아키텍처** | 일반적으로 검색되어 자동으로 채워지며 그렇지 않으면 32비트 또는 64비트가 지정됩니다. |
| **경로 환경 변수** | 인터프리터에서 검색 경로를 찾는 데 사용하는 환경 변수입니다. Visual Studio는 Python을 시작할 때 변수 값을 변경하여 프로젝트의 검색 경로를 포함하도록 합니다. 일반적으로 이 속성은 `PYTHONPATH`로 설정해야 하지만 일부 인터프리터에서는 다른 값을 사용합니다. |

### <a name="pip-tab"></a>pip 탭

환경에 설치된 패키지를 관리하여 종속성을 비롯한 새 패키지를 검색 및 설치할 수 있습니다. 검색을 수행하면 현재 설치된 패키지를 필터링할 뿐만 아니라 [PyPI](https://pypi.python.org)를 검색할 수 있습니다. 검색 상자에 `--user` 또는 `--no-deps` 등의 플래그를 포함하여 `pip install` 명령을 직접 입력할 수도 있습니다.

![Python 환경 pip 탭](~/python/media/environments-pip-tab.png)

### <a name="intellisense-tab"></a>IntelliSense 탭

IntelliSense 완성 데이터베이스의 현재 상태를 보여 줍니다.

![Python 환경 IntelliSense 탭](~/python/media/environments-intellisense-tab.png)

데이터베이스에는 모든 환경의 라이브러리에 대한 메타데이터가 포함되며 IntelliSense 속도가 향상되고 메모리 사용량이 줄어듭니다. Visual Studio에서 새 환경을 검색하거나 사용자가 환경을 추가하면 라이브러리 소스 파일을 분석하여 데이터베이스 컴파일을 자동으로 시작합니다. 이 프로세스는 설치된 항목에 따라 1분에서 1시간 또는 그 이상이 소요될 수 있습니다. (예를 들어 Anaconda에는 많은 라이브러리가 함께 제공되며 데이터베이스를 컴파일하는 데 다소 시간이 소요됩니다.) 완료되면 자세한 IntelliSense를 얻게 되며 더 많은 라이브러리를 설치할 때까지 데이터베이스를 다시 새로 고치지 않아도 됩니다(**DB 새로 고침** 단추 사용).

컴파일되지 않은 데이터에 대한 라이브러리는 **!**로 표시되며 환경의 데이터베이스가 완료되지 않은 경우 주 환경 목록에서 데이터베이스 옆에도 **!** 가 표시됩니다.

## <a name="global-environments"></a>글로벌 환경

글로벌(또는 시스템 차원) 환경은 컴퓨터의 모든 프로젝트에 사용 가능합니다. 일반적으로 Visual Studio는 자동으로 글로벌 환경을 검색하며 Python 환경 창에서 이를 볼 수 있습니다. 그렇지 않은 경우 [Visual Studio에서 Python 환경 관리](#managing-python-environments-in-visual-studio)에서 설명한 것처럼 수동으로 환경을 추가할 수 있습니다.

Visual Studio는 실행, 디버깅, 구문 검사, 가져오기 및 멤버 완성 표시 및 환경이 필요한 기타 모든 작업을 위한 새로운 모든 프로젝트에 대해 기본 환경을 사용합니다. 기본 환경을 변경하면 [프로젝트별 환경](#project-specific-environments)이 추가되지 않은 모든 프로젝트에 영향을 주며 이에 대해서는 다음에 설명합니다.

## <a name="project-specific-environments"></a>프로젝트별 환경

프로젝트별 환경은 기본 글로벌 환경은 무시하고 프로젝트가 항상 특정 환경에서 실행되도록 합니다. 예를 들어 글로벌 기본 환경이 CPython이지만 프로젝트에 IronPython과 글로벌 환경에 설치되지 않은 특정 라이브러리가 필요한 경우 프로젝트별 환경이 필요합니다.

프로젝트 환경은 솔루션 탐색기에서 Python 환경 노드 아래 나열됩니다. 굵게 표시된 항목은 현재 활성 상태이며 디버깅 가져오기 및 멤버 완성, 구문 검사 및 환경이 필요한 기타 모든 작업에 사용됩니다.

![프로젝트 환경이 솔루션 탐색기에 표시됨](media/environments-project.png)

프로젝트에 대해 서로 다른 환경을 활성화하려면 해당 환경을 마우스 오른쪽 단추로 클릭하고 **Activate Environment**(환경 활성화)를 선택합니다.

**Python 환경**을 마우스 오른쪽 단추로 클릭하고 **Add/Remove Python Environments...**(Python 환경 추가/제거...)를 선택하여 모든 글로벌 환경을 프로젝트 환경으로 추가할 수 있습니다. 표시된 목록에서 사용자 프로젝트에 사용 가능한 환경을 선택하거나 선택 취소할 수 있습니다.

![Python 환경 추가/제거 대화 상자](~/python/media/environments-add-remove.png)

솔루션 탐색기에서 환경을 확장하여 설치된 패키지를 표시할 수도 있습니다(환경이 활성 상태일 때 가져와 코드에서 사용할 수 있음).

![솔루션 탐색기에서 환경에 대한 Python 패키지](~/python/media/environments-installed-packages.png)

새 패키지를 설치하려면 환경을 마우스 오른쪽 단추로 클릭하고 **Python 패키지 설치...**를 선택하고 원하는 패키지 이름을 입력합니다. 패키지(및 종속성)은 [Python 패키지 인덱스(PyPI)](https://pypi.python.org/pypi)에서 다운로드하며 여기에서 사용 가능한 패키지의 검색도 가능합니다. Visual Studio의 상태 표시줄 및 출력 창에 설치에 대한 정보가 표시됩니다. 패키지를 제거하려면 마우스 오른쪽 단추로 클릭하고 **제거**를 선택합니다.

> [!Note]
> Python의 패키지 관리 지원은 코어 Python 개발 팀에서 현재 개발 중입니다. 표시된 항목은 정확하지 않을 수 있으며 설치 및 설치 제거가 안정적이지 않거나 사용 가능하지 않을 수 있습니다. Visual Studio는 pip 패키지 관리자(가능한 경우)를 사용하며 필요할 경우 다운로드하여 설치합니다. 또한 Visual Studio는 easy_install 패키지 관리자도 사용할 수 있습니다. 명령줄에서 pip 또는 easy_install을 사용하여 설치된 패키지도 표시됩니다.

> [!Tip]
> pip에서 패키지 설치에 실패하는 일반적인 상황은 패키지가 `*.pyd` 파일에 기본 구성 요소에 대한 소스 코드를 포함하는 경우입니다. 필요한 Visual Studio 버전이 설치되지 않으면 pip에서 해당 구성 요소를 컴파일할 수 없게 됩니다. 이 경우 표시된 오류 메시지는 `error: Unable to find vcvarsall.bat.`입니다. 보통 `easy_install`은 미리 컴파일된 이진 파일을 다운로드할 수 있으며 [http://aka.ms/VCPython27](http://aka.ms/VCPython27)에서 이전 버전의 Python에 적합한 컴파일러를 다운로드할 수 있습니다. 자세한 내용은 Python 도구 팀 블로그에서 ["vcvarsallbat을 찾을 수 없는" 어려움을 해결하는 방법](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/)(영문)을 참조하세요.


## <a name="virtual-environments"></a>가상 환경

글로벌 환경에 설치된 패키지는 해당 패키지를 사용하는 모든 프로젝트에서 사용 가능하므로 두 프로젝트에 호환되지 않은 패키지 또는 동일한 패키지의 서로 다른 버전이 필요한 경우 충돌이 발생할 수 있습니다. 이러한 충돌을 피하기 위해 Visual Studio에서 *가상 환경*을 만드는 기능을 제공하며 이러한 환경은 일반적으로 프로젝트에 국한됩니다.

다른 Python 환경처럼 가상 환경은 Python 인터프리터, 라이브러리 및 패키지 집합으로 구성됩니다. 하지만 이 경우 가상 환경은 글로벌 환경(가상 환경을 지원한다면) 중 하나의 인터프리터 및 라이브러리를 사용하지만 패키지는 글로벌 및 다른 모든 가상 환경과 별도로 격리됩니다. 마찬가지로 충돌을 방지하며 가상 환경의 공간을 최소화하여 패키지의 크기를 적절히 조정합니다. 

가상 환경을 만들려면

1. 솔루션 탐색기에서 **Python 환경**을 마우스 오른쪽 단추로 클릭하고 **Add Virtual Environment...**(가상 환경 추가...)를 선택하면 다음이 표시됩니다.

    ![가상 환경 만들기](~/python/media/environments-add-virtual-1.png)

1. 프로젝트 경로에 가상 환경을 만들 이름을 지정하고 다른 위치에 만들려면 전체 경로를 지정합니다. (다른 도구와 최대 호환성을 보장하려면 이름에 문자와 숫자만 사용하세요.)

1. 기본 인터프리터로 글로벌 환경을 선택하고 **만들기**를 클릭합니다. `pip` 및 `virtualenv` 또는 `venv` 패키지를 사용할 수 없는 경우 다운로드하여 설치합니다.

    제공된 경로가 기존 가상 환경인 경우 기본 인터프리터가 검색되고 만들기 단추가 **추가**로 변경됩니다.

    ![기존 환경 추가](~/python/media/environments-add-virtual-2.png)

솔루션 탐색기에서 **Python 환경**을 마우스 오른쪽 단추로 클릭하거나 **기존 가상 환경 추가...**를 선택하여 기존 가상 환경을 추가할 수도 있습니다. Visual Studio는 환경의 `lib` 디렉터리에서 `orig-prefix.txt` 파일을 사용하여 기본 인터프리터를 검색합니다.

가상 환경이 프로젝트에 추가되면 **Python 환경** 창에 나타나며 다른 환경처럼 프로젝트를 활성화하고 해당 패키지를 관리할 수 있습니다. 마우스 오른쪽 단추로 클릭하고 **제거**를 클릭하면 해당 환경에 대한 참조가 제거되거나 해당 환경 및 디스크의 모든 파일이 삭제됩니다(물론, 기본 인터프리터는 제외).

가상 환경에 대한 한 가지 단점은 하드 코드된 파일 경로를 포함하므로 다른 개발 컴퓨터와 쉽게 공유하거나 전송할 수 없다는 점입니다. 다행히, `requirements.txt` 파일을 사용할 수 있는데, 이에 대한 내용은 다음 섹션에서 설명합니다.

## <a name="managing-required-packages"></a>필수 패키지 관리

빌드 시스템을 사용하여 다른 사람과 프로젝트를 공유하거나 [Microsoft Azure에 게시](template-azure-cloud-service.md)할 계획인 경우 필요한 외부 패키지를 지정해야 합니다. 권장되는 방법은 필요한 종속 패키지 버전을 설치하는 pip 명령 목록이 들어 있는 [requirements.txt 파일](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files)(readthedocs.org)을 사용하는 것입니다.

기술적으로, 파일 이름을 사용하여 요구 사항을 추적할 수 있으나(패키지 설치 시 `-r <full path to file>` 사용) Visual Studio에서 `requirements.txt`에 대한 구체적인 지원을 제공합니다.

- `requirements.txt`가 포함된 프로젝트를 로드하고 해당 파일에 나열된 모든 패키지를 설치하려는 경우 프로젝트를 마우스 오른쪽 단추로 클릭하고 **requirements.txt에서 설치**를 선택합니다.

    ![requirements.txt에서 설치](~/python/media/environments-requirements-txt-install.png)

- 프로젝트에 필요한 모든 패키지가 설치되었으면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **requirements.txt 생성**을 선택하여 필요한 파일을 만듭니다. 파일이 이미 있는 경우 업데이트 방법을 묻는 메시지가 표시됩니다.

    ![requirements.txt 옵션 업데이트](~/python/media/environments-requirements-txt-replace.png)

    - **전체 파일 바꾸기**는 존재하는 모든 항목, 주석 및 옵션이 제거됩니다.
    - **기존 항목 새로 고침**은 패키지 요구 사항을 검색하고 버전 지정자를 현재 설치된 버전에 맞게 업데이트합니다.
    - **항목 업데이트 및 추가**는 확인된 요구 사항을 새로 고치고 모든 다른 패키지를 파일 끝에 추가합니다.

`requirements.txt` 파일은 프로젝트의 요구 사항을 동결하기 위해 작성된 것이므로 모든 설치된 패키지가 정확한 버전으로 작성됩니다. 이렇게 하면 다른 컴퓨터에서 사용자 환경을 쉽게 재현할 수 있습니다. 패키지는 다른 패키지의 종속성으로 버전 범위로 되거나 pip 이외의 설치 관리자로 설치된 경우에도 포함됩니다.

새 가상 환경을 추가할 때 ` requirements.txt` 파일이 존재하면 **가상 환경 추가** 대화 상자에 패키지를 자동으로 설치하는 옵션이 표시되어 다른 컴퓨터에서 환경을 쉽게 다시 만들 수 있습니다.

![requirements.txt로 가상 환경 만들기](~/python/media/environments-requirements-txt.png)

pip로 패키지를 설치할 수 없고 `requirements.txt` 파일에 나타나는 경우 전체 설치에 실패합니다. 이 경우 이 패키지를 제외하도록 수동으로 파일을 편집하거나 패키지의 설치 가능한 버전을 참조하도록 [pip의 옵션](http://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format)을 사용합니다. 예를 들어 [`pip wheel`](http://pip.readthedocs.org/en/latest/reference/pip_wheel.html)을 사용하여 종속성을 컴파일하고 `--find-links <path>` 옵션을 사용자의 `requirements.txt`에 추가하는 것이 좋습니다.

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

# <a name="search-paths"></a>검색 경로

일반적인 Python 사용에서 `PYTHONPATH` 환경 변수(또는 `IRONPYTHONPATH` 등)는 모듈 파일에 대한 기본 검색 경로를 제공합니다. 즉, `import <name>` 문을 사용할 때 Python은 일치하는 이름에 대해 기본 제공 모듈을 먼저 검색한 후 실행 중인 Python 코드가 들어 있는 폴더를 검색하고, 적용 가능한 환경 변수에 정의된 대로 "모듈 검색 경로"를 검색합니다. (코어 Python 설명서의 [모듈 검색 경로](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) 및 [환경 변수](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) 참조)

하지만 검색 경로 환경 변수는 전체 시스템에 대해 설명된 경우에도 Visual Studio에서 무시됩니다. 이렇게 무시되는 이유는 실제로 엄밀히 말해 전체 시스템에 대해 설명되었기 *때문이며* 따라서 자동으로 해결할 수 없는 다음과 같은 특정 질문이 제기된다. 참조된 모듈이 Python 2.7 또는 Python 3.3용인가? 이 모듈이 표준 라이브러리 모듈을 재정의하게 되는가? 개발자가 이를 알고 있는가 아니면 악의적인 하이재킹 시도인가?

따라서 Visual Studio에서 Python 지원은 환경 및 프로젝트 모두에서 검색 경로를 직접 지정하는 방법을 제공합니다. 이러한 내용은 Visual Studio에서 스크립트를 디버깅 또는 실행할 때 `PYTHONPATH`(또는 이와 동등한)의 값으로 전달됩니다. Visual Studio는 검색 경로를 추가하여 해당 위치의 라이브러리를 검사하고 라이브러리에 대한 IntelliSense 데이터베이스를 빌드합니다(라이브러리 수에 따라 다소 시간이 걸릴 수 있음).

검색 경로를 추가하려면 솔루션 탐색기에서 **검색 경로** 항목을 마우스 오른쪽 단추로 클릭하고 **검색 경로에 폴더 추가...**를 선택하고 포함할 폴더를 선택합니다. 이 경로는 프로젝트와 연결된 환경에 사용됩니다.

`.zip` 또는 `.egg` 확장명이 있는 파일도 **검색 경로에 Zip 보관 파일 추가...**를 선택하여 검색 경로로 추가할 수 있습니다. 폴더와 마찬가지로 이러한 폴더의 내용을 검색하고 IntelliSense에 제공합니다.

> [!Note]
> Python 3.3을 사용하는 동안 Python 2.7 모듈에 대한 검색 경로를 추가할 수 있으며 그 결과 오류가 표시될 수 있습니다.

정기적으로 동일한 검색 경로를 사용하고 그 내용이 자주 변경되지 않는 경우 site-packages 폴더에 설치하는 것이 더 효율적일 수 있습니다. 그러면 분석되어 IntelliSense 데이터베이스에 저장되며 항상 의도한 환경과 연결되고 각 프로젝트에 대해 검색 경로를 추가할 필요가 없습니다.

