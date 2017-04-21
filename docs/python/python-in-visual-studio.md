---
title: "Visual Studio에서 Python | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f4f6fb-0ae4-4234-9df2-531f2d3af17f
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
translationtype: Human Translation
ms.sourcegitcommit: 06f5b9d2223ccb9cbbbff8f2960d89c8efbf05b2
ms.openlocfilehash: 83a676c5f2f838b6920c5fafbe78dc9b49fbb4cb
ms.lasthandoff: 04/12/2017

---

# <a name="working-with-python-in-visual-studio"></a>Visual Studio에서 Python 작업

Python은 안정적이고, 유연하고, 배우기 쉽고, 모든 운영 체제에서 무료로 사용할 수 있고, 강력한 개발자 커뮤니티에서 지원하고, 많은 무료 라이브러리가 제공되는 널리 사용되는 프로그래밍 언어입니다. Python은 웹 응용 프로그램, 웹 서비스, 데스크톱 앱, 스크립팅 및 과학적 컴퓨팅 등 모든 방식의 개발을 지원하며 대학, 과학자, 아마추어 개발자 및 전문 개발자 등 많은 분야에 사용됩니다. [python.org](https://www.python.org) 및 [Python for Beginners](https://www.python.org/about/gettingstarted/)(초보자를 위한 Python)에서 이 언어에 대해 자세히 알아볼 수 있습니다.

Visual Studio는 Python 워크로드(Visual Studio 2017)와 무료 Visual Studio용 Python 도구 확장(Visual Studio 2015 및 이전 버전)을 통해 Python 언어에 대한 [오픈 소스](https://github.com/Microsoft/ptvs) 지원을 제공합니다. 

[설치 지침](installation.md)에 따라 Python 워크로드를 설치한 후 아래 링크를 사용하여 Python 관련 기능 및 Visual Studio 자체 기능에 대해 자세히 알아봅니다.

| 기능 | 설명 | 일반 Visual Studio 설명서 | 
| --- | --- | --- |
| [Visual Studio 프로젝트 시스템](python-projects.md) | Python 코드의 폴더 구조를 암시적으로 선택할 뿐만 아니라 앱 코드, 테스트 코드, 웹 페이지, JavaScript, 빌드 스크립트 등을 식별할 수 있도록 명시적으로 제어할 수 있습니다. | [Visual Studio의 솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md) |
| [프로젝트 템플릿](python-projects.md#project-templates) | 콘솔, 웹, Azure, 데이터 과학 및 기타 형식의 프로젝트에 대한 프로젝트 구조를 신속하게 만듭니다. | [Visual Studio 템플릿](../ide/creating-project-and-item-templates.md#visual-studio-templates) |
| 다양한 인터프리터 지원 | CPython 및 IronPython의 다양한 버전을 지원합니다. | 해당 없음 |
| IPython 지원 | 인라인 플롯, .NET 및 WPF(Windows Presentation Foundation)에 대한 REPL의 IPython/Jupyter에 대한 지원을 포함합니다. | 해당 없음 |
| [다양한 편집 기능, IntelliSense 및 코드 이해](code-editing.md) | 구문 색 지정, 모든 코드 및 라이브러리에 대한 자동 완성, [코드 서식 지정](code-formatting.md), 시그니처 도움말, 클래스 뷰, 정의로 이동, 모든 참조 찾기, 코드 조각, [리팩터링](code-refactoring.md), [PyLint](code-pylint.md) 등을 포함합니다. | [코드 및 텍스트 편집기에서 코드 작성](../ide/writing-code-in-the-code-and-text-editor.md) |
| [대화형 창](interactive-repl.md) | 코드 부분을 간편하게 강조 표시하고 이를 대화형 창으로 보내는 기능을 포함하는 Python에 대한 신속한 REPL 환경을 제공합니다. | 해당 없음 |
| [완전한 기능의 디버깅](debugging.md) | Visual Studio 프로젝트 유무에 관계 없이 풍부한 디버깅이 가능하며, 기존 실행 파일에 대한 기능, [Python/C++ 혼합 모드 디버깅](debugging-mixed-mode.md), Windows/Linux/Mac으로 [원격 디버깅](debugging-cross-platform-remote.md), [Azure로 원격 디버깅](debugging-azure-remote.md) 및 대화형 창 내에서 디버깅 등을 수행할 수 있습니다. | [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md) |
| [포괄적인 보고를 제공하는 프로파일링 도구](profiling.md) | 서로 다른 프로파일링 실행 간에 성능을 비교하는 기능을 포함하여 응용 프로그램 내에서 시간이 어떻게 소요되는지 살펴봅니다. | [프로파일링 도구](../profiling/profiling-tools.md)(Python에 대해 일부 Visual Studio 프로파일링 기능만 사용할 수 있음) |
| [단위 테스트 도구](unit-testing.md) | Visual Studio 테스트 탐색기에서 테스트를 검색, 실행 및 관리하고 단위 테스트를 쉽게 디버깅합니다. | [코드 단위 테스트](../test/unit-test-your-code.md) |

또한 Python 워크로드는 Windows, Mac OS X 및 Linux에 대한 지원과 함께 Azure 서비스 사용을 간소화하는 [Python용 Azure SDK](azure-sdk-for-python.md)도 포함합니다.

주요 기능에 대한 개요를 제공하는 YouTube의 [getting started and deep dive videos](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)(시작 및 자세히 알아보기 동영상) 시리즈입니다.

[![Python 도구 동영상](media/video-general.png)](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)

## <a name="questions-and-answers"></a>질문과 대답

**질문: UI를 빌드하는 데 Python과 함께 무엇을 사용할 수 있나요?**

대답: 이 영역의 기본 제품은 [Qt Project](https://www.qt.io/qt-for-application-development/), [PySide(공식 바인딩)](http://wiki.qt.io/PySide)([PySide 다운로드](https://download.qt.io/official_releases/pyside/.)도 참조)로 알려진 Python용 바인딩 및 [PyQt](https://wiki.python.org/moin/PyQt)입니다. 현재는 Visual Studio의 Python 지원에 UI 개발용 특정 도구가 포함되지 않습니다.

**질문: Python 프로젝트에서 독립 실행형 실행 파일을 생성할 수 있나요?**

대답: Python은 일반적으로 Visual Studio 및 웹 서버와 같은 Python을 사용할 수 있는 적합한 환경에서 요청 시 실행되는 코드를 포함하는 해석된 언어입니다. 현재는 Visual Studio 자체에서 독립 실행형 실행 파일을 만드는 방법을 제공하지 않습니다. 즉, 기본적으로 포함된 Python 인터프리터가 있는 프로그램입니다. 그러나 [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency)에 설명된 것처럼 Python 커뮤니티 내에 이렇게 하는 다양한 방법이 있습니다. 또한 CPython은 블로그 게시물 [Using CPython's Embeddable Zip File](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/)(CPython의 포함 가능한 Zip 파일 사용)에 설명된 것처럼 네이티브 응용 프로그램 내에 포함되는 기능을 지원합니다.

## <a name="features-matrix"></a>기능 매트릭스

[설치 가이드](installation.md)에 설명된 대로 Visual Studio의 다음 버전(edition)에 Python 지원을 설치할 수 있습니다.

- [Visual Studio 2017 Preview](https://www.visualstudio.com/vs/preview)
- [Visual Studio 2015(모든 버전)] (https://www.visualstudio.com/ko-kr/downloads/visual-studio-2015-downloads-vs)
- [Visual Studio 2013 Community Edition] (https://www.visualstudio.com/ko-kr/products/visual-studio-community-vs.aspx)
- [Visual Studio 2013 Express for Web, Update 2 이상](https://www.microsoft.com/en-us/download/details.aspx?id=44912)
- [Visual Studio 2013 Express for Desktop, Update 2 이상](https://www.microsoft.com/en-US/download/details.aspx?id=44914)
- Visual Studio 2013(Pro 버전 이상)
- Visual Studio 2012(Pro 버전 이상)
- Visual Studio 2010 SP1(Pro 버전 이상, .NET 4.5 필요)

Visual Studio 버전(version 및 edition)에서 지원되는 기능:

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
| 웹 사이트에 웹 배포 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| 웹 역할에 웹 배포 | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| 작업자 역할에 웹 배포 | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
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

1. VS 2012에 대한 Git 지원은 Git용 Visual Studio 도구 확장에서 사용 가능하며 [Visual Studio 갤러리](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c)에서 제공됩니다.

2. Azure 웹 사이트에 배포하려면 [.NET 2.1용 Azure SDK - VS 2010 SP1](http://go.microsoft.com/fwlink/?LinkId=313855)이 필요합니다.  이상 버전에서는 VS 2010을 지원하지 않습니다.

3. Azure 웹 역할 및 작업자 역할에 대한 지원을 사용하려면 [.NET 2.3용 Azure SDK - VS 2012](http://go.microsoft.com/fwlink/?LinkId=323511) 이상이 필요합니다.

4. Azure 웹 역할 및 작업자 역할에 대한 지원을 사용하려면 [.NET 2.3용 Azure SDK - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

5. Visual Studio 2013에서 Django 템플릿 편집기에는 몇 가지 알려진 문제가 있으며 Update 2를 설치하여 해결할 수 있습니다.

6. Windows 8 이상이 필요합니다. Visual Studio 2013 Express for Web에는 [프로세스에 연결] 대화 상자가 없지만 Azure 웹 사이트 원격 디버깅은 서버 탐색기에서 Attach Debugger(Python) 명령을 사용하여 계속 수행할 수 있습니다. 이렇게 하려면 [.NET 2.3용 Azure SDK - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

7. Windows 8 이상이 필요합니다. 서버 탐색기에서 Attach Debugger(Python) 명령을 사용하려면 [.NET 2.3용 Azure SDK - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) 이상이 필요합니다.

8. Windows 8 이상이 필요합니다.

## <a name="additional-resources"></a>추가 리소스

- [PyKinect를 사용하여 Python으로 Kinect games 게임 작성](https://github.com/Microsoft/PTVS/wiki/PyKinect)(영문)(GitHub wiki)
- [IIS 및 Python 간 WFastCGI 브리지](https://pypi.python.org/pypi/wfastcgi)(영문)(python.org)

