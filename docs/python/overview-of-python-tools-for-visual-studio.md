---
title: Windows의 Visual Studio에서 Python 지원 개요
description: Windows에서 최상의 Python IDE(PTVS(Visual Studio용 Python 도구)로도 알려짐)로 만드는 Visual Studio의 Python 기능에 대한 요약입니다.
ms.date: 04/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 44d2e6c20173c075f1a3e5aac4881f12f5b46e1f
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="working-with-python-in-visual-studio-on-windows"></a>Visual Studio에서 Python 작업(Windows)

Python은 안정적이고 유연하며 배우기 쉬울뿐만 아니라 모든 운영 체제에서 무료로 사용할 수 있으며, 유용한 개발자 커뮤니티와 다양한 무료 라이브러리에서 지원되며 널리 사용되는 프로그래밍 언어입니다. Python은 웹 응용 프로그램, 웹 서비스, 데스크톱 앱, 스크립팅 및 과학적 컴퓨팅 등 모든 방식의 개발을 지원하며 대학, 과학자, 아마추어 개발자 및 전문 개발자 등 많은 분야에 사용됩니다. [python.org](https://www.python.org) 및 [Python for Beginners](https://www.python.org/about/gettingstarted/)(초보자를 위한 Python)에서 이 언어에 대해 자세히 알아볼 수 있습니다.

Visual Studio는 Windows에서 강력한 Python IDE입니다. Visual Studio는 Python 개발 및 데이터 과학 워크로드(Visual Studio 2017)와 무료 Visual Studio용 Python 도구 확장(Visual Studio 2015 및 이전 버전)을 통해 Python 언어에 대한 [오픈 소스](https://github.com/Microsoft/ptvs) 지원을 제공합니다.

Python은 현재 Mac용 Visual Studio에서 지원되지 않지만 Visual Studio Code를 통해 Mac 및 Linux에서 사용할 수 있습니다([질문 및 답변](#questions-and-answers) 참조).

시작하려면 다음을 수행합니다.

- [설치 지침](installing-python-support-in-visual-studio.md)에 따라 Python 워크로드를 설치합니다.
- 이 문서의 섹션을 통해 Visual Studio의 Python 기능을 숙지합니다. Visual Studio의 Python 소개 [비디오 시리즈(Microsoft Virtual Academy)를 시청](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121)할 수 있습니다(총 22분).
- 빠른 시작을 하나 이상 수행하여 프로젝트를 만듭니다. 확실하지 않은 경우 [Flask를 사용하여 웹앱 만들기](../ide/quickstart-python.md?context=visualstudio/python/default)부터 시작합니다.
- 전체 종단 간 환경을 위한 [Visual Studio에서 Python 사용](tutorial-working-with-python-in-visual-studio-step-01-create-project.md) 자습서를 수행합니다.

## <a name="support-for-multiple-interpreters"></a>다중 인터프리터 지원.

Visual Studio의 **Python 환경** 창(넓게 확장된 뷰에서 아래에 표시)은 전역 Python 환경, Conda 환경 및 가상 환경 모두를 관리하기 위한 단일 위치를 제공합니다. Visual Studio는 자동으로 기본 위치에 Python 설치를 검색하고 사용자 지정 설치를 구성할 수 있습니다. 각 환경을 사용하여 패키지를 쉽게 관리하고 해당 환경에 대한 대화형 창을 열고 환경 폴더에 액세스할 수 있습니다.

![Python 환경 창의 확장된 뷰](media/environments-expanded-view.png)

추가 정보

- 비디오(2분 35초): [Python 환경 관리](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)
- Docs: [Python 환경 관리](managing-python-environments-in-visual-studio.md)
- Docs: [Python 환경 창 참조](python-environments-window-tab-reference.md)

## <a name="rich-editing-intellisense-and-code-comprehension"></a>다양한 편집 기능, IntelliSense 및 코드 이해

Visual Studio에서는 구문 색 지정, 모든 코드 및 라이브러리에 대한 자동 완성 기능, 코드 서식 지정, 서명 도움말, 리팩터링, Lint(아래 참조) 및 형식 힌트를 포함하는 고급 Python 편집기를 제공합니다. Visual Studio에서 클래스 뷰, 정의로 이동, 모든 참조 찾기 및 코드 조각 등의 고유한 기능을 제공합니다. [대화형 창](#interactive-window)과 직접 통합하여 파일에 이미 저장되어 있는 Python 코드를 신속히 개발할 수 있습니다.

![Visual Studio에서 Python 코드에 대한 코드 완성](media/code-editing-completions-simple.png)

추가 정보

- 동영상(2분 30초): [Python 코드 편집](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567)
- Docs: [Python 코드 편집](editing-python-code-in-visual-studio.md)
- Docs: [코드 서식 지정](formatting-python-code.md)
- Docs: [리팩터링](refactoring-python-code.md)
- Docs: [Lint](linting-python-code.md)
- 일반 Visual Studio 기능 docs: [코드 및 텍스트 편집기에서 코드 작성](../ide/writing-code-in-the-code-and-text-editor.md)

## <a name="interactive-window"></a>대화형 창

Visual Studio에 알려진 모든 Python 환경의 경우 별도 명령 프롬프트를 사용하는 대신 Visual Studio 내에서 직접 Python 인터프리터에 대한 동일한 대화형(REPL) 환경을 쉽게 열 수 있습니다. 또한 환경 간 전환을 쉽게 할 수 있습니다.

![Visual Studio의 Python 대화형 창](media/interactive-window.png)

또한 Visual Studio는 Python 코드 편집기와 대화형 창 사이의 긴밀한 통합을 제공합니다. **Ctrl + Enter** 키보드 바로 가기 키는 간편하게 편집기에서 현재 코드 줄(또는 코드 블록)을 대화형 창으로 보낸 다음, 다음 줄(또는 블록)로 이동합니다. **Ctrl + Enter** 키를 사용하면 디버거를 실행할 필요 없이 쉽게 한 단계씩 코드를 실행할 수 있습니다. 또한 같은 키 입력으로 대화형 창에 선택한 코드를 보내고 쉽게 대화형 창에서 편집기에 코드를 붙여 넣을 수 있습니다. 이러한 기능을 함께 사용하면 대화형 창에서 코드의 세그먼트에 대한 세부 정보를 파악하고 편집기에서 결과를 파일에 쉽게 저장할 수 있습니다.

또한 Visual Studio는 인라인 플롯, .NET 및 WPF(Windows Presentation Foundation)을 포함한 REPL의 IPython/Jupyter를 지원합니다.

추가 정보

- 동영상(2 분 22초): [Python 대화형 창](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=gJYKY5LWE_4605918567)
- Docs: [대화형 창](python-interactive-repl-in-visual-studio.md)
- Docs: [Visual Studio의 IPython](interactive-repl-ipython.md)

## <a name="project-system-and-project-and-item-templates"></a>프로젝트 시스템, 프로젝트 및 항목 템플릿

Visual Studio에서는 시간이 지남에 따라 커지는 프로젝트의 복잡성을 관리할 수 있습니다. 프로젝트는 폴더 구조보다 훨씬 더 복잡합니다. 곧, 다른 파일이 어떻게 사용되는지 그리고 서로 어떤 관계인지에 대한 이해가 포함됩니다. Visual Studio를 사용하면 앱 코드, 태스트 코드, 웹 페이지, JavaScript, 빌드 스크립트 등을 구분한 다음, 파일에 적합한 기능을 사용하도록 설정할 수 있습니다. 또한 Visual Studio 솔루션에서는 Python 프로젝트 및 C++ 확장 프로젝트 같은 다수의 관련 프로젝트를 관리할 수 있습니다.

![Python 및 C++ 프로젝트가 포함된 Visual Studio 솔루션](media/projects-solution-explorer-two-projects.png)

프로젝트 및 항목 템플릿은 다양한 유형의 프로젝트와 파일의 설정 프로세스를 자동화하여 소중한 시간을 절약해주고 복잡하고 오류가 발생하기 쉬운 세부 정보를 관리할 필요가 없습니다. Visual Studio는 웹, Azure, 데이터 과학, 콘솔 및 기타 유형의 프로젝트에 대한 템플릿뿐 아니라 Python 클래스, 단위 테스트, Azure 웹 구성, HTML 및 Django 앱 같은 파일에 대한 템플릿도 제공합니다.

[![Visual Studio에서 Python 프로젝트 및 항목 템플릿](media/project-and-item-templates.png)](media/project-and-item-templates.png)

추가 정보

- Docs: [Python 프로젝트 관리](managing-python-projects-in-visual-studio.md)
- Docs: [항목 템플릿 참조](python-item-templates.md)
- Docs: [Python 프로젝트 템플릿](managing-python-projects-in-visual-studio.md#project-templates)
- Docs: [C++ 및 Python 작업](working-with-c-cpp-python-in-visual-studio.md)
- 일반 Visual Studio 기능 docs: [프로젝트 및 항목 템플릿](../ide/creating-project-and-item-templates.md#visual-studio-templates)
- 일반 Visual Studio 기능 docs: [Visual Studio의 솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)

## <a name="full-featured-debugging"></a>완전한 기능의 디버깅

Visual Studio의 장점 중 하나는 강력한 디버거입니다. 특히 Python의 경우 Visual Studio는 Python/C++ 혼합 모드 디버깅, Linux에서 원격 디버깅, Azure에서 원격 디버깅, 대화형 창 내에서 디버깅 및 Python 단위 테스트 디버깅을 포함합니다.

![예외 팝업을 표시하는 Python용 Visual Studio 디버거](media/debugging-exception-popup.png)

추가 정보

- 비디오: [Python 디버깅 3분 32초](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=Ep5dp5LWE_3805918567)
- Docs: [Python 디버깅](debugging-python-in-visual-studio.md)
- Docs: [Python/C++ 혼합 모드 디버깅](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- Docs: [Linux에서 원격 디버깅](debugging-python-code-on-remote-linux-machines.md)
- Docs: [Azure에서 원격 디버깅](debugging-remote-python-code-on-azure.md)
- 일반 Visual Studio 기능 docs: [Visual Studio 디버거의 기능 둘러보기](../debugger/debugger-feature-tour.md)

## <a name="profiling-tools-with-comprehensive-reporting"></a>포괄적인 보고를 제공하는 프로파일링 도구

프로파일링은응용 프로그램 내에서 시간이 어떻게 쓰이는지를 탐색합니다. Visual Studio는 CPython 기반 인터프리터를 사용한 프로 파일링을 지원하고 다른 프로파일링 실행 간 성능을 비교하는 기능을 포함합니다.

[![Python 프로젝트에 대한 Visual Studio 프로파일러 결과](media/profiling-results.png)](media/profiling-results.png)

추가 정보

- 비디오: [Python 프로파일링 3분 00초](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567)
- Docs: [Python 프로파일링 도구](profiling-python-code-in-visual-studio.md)
- 일반 Visual Studio 기능 docs: [프로파일링 기능 둘러보기](../profiling/profiling-feature-tour.md). (Python에 대해 일부 Visual Studio 프로파일링 기능만 사용할 수 있습니다).

## <a name="unit-testing-tools"></a>위 테스트 도구

Visual Studio 테스트 탐색기에서 테스트를 검색, 실행 및 관리하고 단위 테스트를 쉽게 디버깅합니다.

![Visual Studio에서 Python 단위 테스트 디버깅](media/unit-test-debugging.png)

추가 정보

- 비디오: [Python 테스트 2분 31초](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567)
- Docs: [Python용 단위 테스트 도구](unit-testing-python-in-visual-studio.md)
- 일반 Visual Studio 기능 docs: [코드 단위 테스트](../test/unit-test-your-code.md).

## <a name="publishing-to-azure-and-azure-sdk-for-python"></a>Python용 Azure SDK 및 Azure에 게시

Visual Studio는 Azure에 웹앱 및 클라우드 서비스를 게시하기 위한 통합 지원을 제공합니다. Visual Studio에는 동적 및 정적 콘텐츠용 필수적인 `web.config` 항목 템플릿이 포함됩니다. 또한 Python 워크로드는 Windows, Mac OS X, Linux 앱에서 Azure 서비스를 간편하게 사용할 수 있도록 해주는 Python용 Azure SDK도 포함합니다.

![Visual Studio에서 Azure에 Python 응용 프로그램 게시](media/azure-publish-dialog.png)

추가 정보

- Docs: [Azure에 게시](publishing-python-web-applications-to-azure-from-visual-studio.md)
- Docs: [Python용 Azure SDK](azure-sdk-for-python.md)

## <a name="python-training-on-microsoft-virtual-academy"></a>Microsoft Virtual Academy의 Python 교육

|   |   |
|---|---|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | <ul><li>[Python을 사용한 프로그래밍 소개](https://mva.microsoft.com/en-US/training-courses/introduction-to-programming-with-python-8360?l=lqhuMxFz_8904984382)</li><li>[Python 초보자: 문자열 및 함수](https://mva.microsoft.com/en-US/training-courses/python-beginner-strings-and-functions-18015)</li><li>[Python 기초: 목록 및 루프](https://mva.microsoft.com/en-US/training-courses/python-fundamentals-lists-and-loops-18019)</li><li>[Python에 대해 가장 많이 하는 질문](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121)</li></ul> |

## <a name="questions-and-answers"></a>질문과 대답

**질문: Mac용 Visual Studio에서 Python 지원을 사용할 수 있나요?**

대답: 이번에는 아니지만 [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac)에 대한 요청을 긍정적으로 평가할 수 있습니다. [Mac용 Visual Studio](/visualstudio/mac/) 설명서에서는 지원되는 현재 개발 유형을 식별합니다. 한편, Windows, Mac 및 Linux의 Visual Studio Code는 [사용 가능한 확장을 통해 Python에서 잘 작동](https://code.visualstudio.com/docs/languages/python)합니다.

**질문: UI를 빌드하는 데 Python과 함께 무엇을 사용할 수 있나요?**

대답: 이 영역의 기본 제품은 [Qt Project](https://www.qt.io/qt-for-application-development/), [PySide(공식 바인딩)](http://wiki.qt.io/PySide)([PySide 다운로드](https://download.qt.io/official_releases/pyside/.)도 참조)로 알려진 Python용 바인딩 및 [PyQt](https://wiki.python.org/moin/PyQt)입니다. 현재는 Visual Studio의 Python 지원에 UI 개발용 특정 도구가 포함되지 않습니다.

**질문: Python 프로젝트에서 독립 실행형 실행 파일을 생성할 수 있나요?**

대답: Python은 일반적으로 Visual Studio, 웹 서버와 같은 적합한 Python 지원 환경에서 요청 시 코드를 실행하는 데 사용되는 해석된 언어입니다. 현재는 Visual Studio 자체에서 독립 실행형 실행 파일을 만드는 방법을 제공하지 않습니다. 즉, 기본적으로 포함된 Python 인터프리터가 있는 프로그램입니다. 그러나 [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency)에 설명된 것처럼 Python 커뮤니티에는 실행 파일을 만드는 다양한 방법이 있습니다. 또한 CPython은 블로그 게시물 [Using CPython's Embeddable Zip File](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/)(CPython의 포함 가능한 Zip 파일 사용)에 설명된 것처럼 네이티브 응용 프로그램 내에 포함되는 기능을 지원합니다.

## <a name="features-matrix"></a>기능 매트릭스

[설치 가이드](installing-python-support-in-visual-studio.md)에 설명된 대로 Visual Studio의 다음 버전(edition)에 Python 기능을 설치할 수 있습니다.

- [Visual Studio 2017(모든 버전)](https://www.visualstudio.com/vs/)
- Visual Studio 2015(모든 버전)
- Visual Studio 2013 Community Edition
- Visual Studio 2013 Express for Web 업데이트 2 이상
- Visual Studio 2013 Express for Desktop 업데이트 2 이상
- Visual Studio 2013(Pro 버전 이상)
- Visual Studio 2012(Pro 버전 이상)
- Visual Studio 2010 SP1(Pro 버전 이상, .NET 4.5 필요)

Visual Studio 2015 및 이전 버전은 [visualstudio.com/vs/older-downloads/](https://www.visualstudio.com/vs/older-downloads/)에서 제공됩니다.

> [!Important]
> 기능이 Visual Studio의 최신 버전에 대해서만 완전하게 지원 및 유지 관리됩니다. 기능이 이전 버전에서 사용할 수 있지만 적극적으로 유지 관리되지 않습니다.

| Python 지원 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 여러 인터프리터 관리 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 자동 검색에 자주 사용되는 인터프리터 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 사용자 지정 인터프리터 추가 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 가상 환경 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Pip/간편 설치 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| 프로젝트 시스템 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 기존 코드에서 새 프로젝트 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 모든 파일 표시 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 소스 제어 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Git 통합 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004;<sup>1</sup> | &#10007; |
<br/>

| 편집 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 구문 강조 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 자동 완성 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 서명 도움말 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 요약 정보 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 개체 브라우저/클래스 뷰 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 탐색 모음 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 정의로 이동 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 다음 탐색 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 모든 참조 찾기 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 자동 들여쓰기 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 코드 서식 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 리팩터링 - 이름 바꾸기 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 리팩터링 - 추출 방법 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 리팩터링 - 가져오기 추가/제거 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PyLint | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| 대화형 창 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 대화형 창 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 인라인 그래프가 있는 IPython | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| 바탕 화면 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 콘솔/Windows 응용 프로그램 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython WPF(XAML 디자이너 포함) | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython Windows Forms | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| 웹 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Django 웹 프로젝트 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Bottle 웹 프로젝트 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Flask 웹 프로젝트 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| 일반 웹 프로젝트 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Azure | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 웹 사이트에 배포 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| 웹 역할에 배포 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| 작업자 역할에 배포 | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Azure 에뮬레이터에서 실행 | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| 원격 디버깅 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> | &#10007; |
| 서버 탐색기 연결 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> | &#10007; | &#10007; |
<br/>

| Django 템플릿 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 디버깅 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| 자동 완성 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004; | &#10004; |
| CSS 및 JavaScript 자동 완성 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007; | &#10007; |
<br/>

| 디버깅 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 디버깅 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 프로젝트 없이 디버깅 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| 디버깅 - 편집에 연결 | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| 혼합 모드 디버깅 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| 원격 디버깅(Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| 디버그 대화형 창 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

<a name="matrix-profiling"></a>

| 프로파일링 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| 프로파일링 | &#10004; | &#10004; | &#10004; | &#10007; | &#10007; | &#10004; | &#10004; | &#10004; |
<br/>

| 테스트 | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 테스트 탐색기 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| 테스트 실행 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| 테스트 디버깅 | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
<br/>

1. Visual Studio 2012에 대한 Git 지원은 Git용 Visual Studio Tools 확장에서 사용 가능하며 [Visual Studio 갤러리](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c)에서 제공됩니다.

1. Azure 웹 사이트에 배포하려면 [.NET 2.1용 Azure SDK - Visual Studio 2010 SP1](http://go.microsoft.com/fwlink/?LinkId=313855)이 필요합니다. 이후 버전에서는 Visual Studio 2010을 지원하지 않습니다.

1. Azure 웹 역할 및 작업자 역할에 대한 지원을 사용하려면 [.NET 2.3용 Azure SDK - VS 2012](http://go.microsoft.com/fwlink/?LinkId=323511) 이상이 필요합니다.

1. Azure 웹 역할 및 작업자 역할에 대한 지원을 사용하려면 [.NET 2.3용 Azure SDK - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

1. Visual Studio 2013에서 Django 템플릿 편집기에는 몇 가지 알려진 문제가 있으며 Update 2를 설치하여 해결할 수 있습니다.

1. Windows 8 이상이 필요합니다. Visual Studio 2013 Express for Web에는 [프로세스에 연결] 대화 상자가 없지만 Azure 웹 사이트 원격 디버깅은 서버 탐색기에서 Attach Debugger(Python) 명령을 사용하여 계속 수행할 수 있습니다. 원격 디버깅을 사용하려면 [.NET 2.3용 Azure SDK - Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

1. Windows 8 이상이 필요합니다. 서버 탐색기에서 Attach Debugger(Python) 명령을 사용하려면 [.NET 2.3용 Azure SDK - Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

1. Windows 8 이상이 필요합니다.

## <a name="additional-resources"></a>추가 자료

- [IIS 및 Python 간 WFastCGI 브리지](https://pypi.org/p/wfastcgi)(pypi.org)
- [Microsoft Virtual Academy의 무료 Python 코스](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Microsoft Virtual Academy의 상위 Python 질문](https://aka.ms/mva-top-python-questions)
