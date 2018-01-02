---
title: "Visual Studio에서 C++ 시작 | Microsoft Docs"
ms.custom: mvc
ms.date: 12/04/2017
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 99c73344-86ba-4b08-9e15-f6111cc04185
author: corob-msft
ms.author: tglee
manager: ghogen
ms.openlocfilehash: c86e7bcfe43eeaa6554efeed6654f34e140d9ea7
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2017
---
# <a name="get-started-with-c-in-visual-studio"></a>Visual Studio에서 C++ 시작

이 빠른 시작을 완료하면 Visual Studio를 사용하여 C++로 응용 프로그램을 개발할 때 사용할 수 있는 여러 도구 및 대화 상자에 익숙해집니다. 간단한 "Hello, World" 스타일 콘솔 응용 프로그램을 만들면서 IDE(통합 개발 환경)에서 작업하는 방법을 배워 보겠습니다.

## <a name="prerequisites"></a>필수 구성 요소

이 빠른 시작을 완료하려면 C++에 익숙하지 않아도 되지만 몇 가지 일반적인 프로그래밍 및 디버깅 개념을 잘 알고 있어야 합니다. Visual Studio 설명서에서는 C++로 프로그래밍하는 방법을 설명하지 않습니다. C++ 학습 리소스에 도움이 되는 가이드는 ISO C++ 웹 사이트의 [시작](https://isocpp.org/get-started) 페이지에 있습니다.

단계를 따르려면 **C++를 사용한 데스크톱 개발** 워크로드가 설치된 Visual Studio 2017 버전 15.3 이상의 복사본이 필요합니다. 빠른 설치 가이드는 [Visual Studio에서 C++ 지원 설치](/cpp/build/vscpp-step-0-installation)를 참조하세요.

## <a name="create-a-console-app"></a>콘솔 앱 만들기

Visual Studio를 아직 실행하지 않는 경우 시작합니다.

![Visual C&#43;&#43; 설정이 적용된 IDE](../ide/media/get-started-cpp-ide-layout.png "Visual C&#43;&#43; 설정이 적용된 IDE")

Visual Studio를 열면 IDE의 세 가지 기본 부분인 도구 창, 메뉴 및 도구 모음, 주 창 공간을 확인할 수 있습니다. 도구 창은 앱 창의 왼쪽과 오른쪽에 고정됩니다. **빠른 실행** 상자, 메뉴 모음 및 표준 도구 모음은 맨 위에 표시됩니다. 창의 가운데에는 **시작 페이지**가 있습니다. 솔루션 또는 프로젝트를 열면 편집기와 디자이너가 이 공간에 나타납니다. 앱을 개발할 때 이 중앙 영역을 가장 많이 사용합니다.

Visual Studio는 *프로젝트*를 사용하여 앱에 대한 코드를 구성하고 *솔루션*을 사용하여 프로젝트를 구성합니다. 프로젝트에는 앱을 빌드하는 데 사용되는 모든 옵션, 구성 및 규칙이 포함됩니다. 또한 프로젝트의 모든 파일과 외부 파일 간의 관계를 관리합니다. 앱을 만들려면 먼저 새 프로젝트 및 솔루션을 만듭니다.

### <a name="to-create-a-console-app-project"></a>콘솔 앱 프로젝트를 만들려면

1. 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.

   ![메뉴 모음에서 파일 > 새로 만들기 > 프로젝트를 선택합니다.](../ide/media/get-started-cpp-file-new-project-menu.png "메뉴 모음에서 파일 > 새로 만들기 > 프로젝트를 선택합니다.")

1. 아직 선택하지 않은 경우 **새 프로젝트** 대화 상자에서 **설치됨 > Visual C++**를 선택합니다. 가운데 창에서 **Windows 콘솔 응용 프로그램** 템플릿을 선택합니다. **이름** 편집 상자에서 *HelloApp*을 입력합니다.

   ![새 프로젝트 대화 상자를 사용하여 앱 프로젝트를 만듭니다.](../ide/media/get-started-cpp-new-project-dialog.png "새 프로젝트 대화 상자를 사용하여 앱 프로젝트를 만듭니다.")

   대화 상자는 이전에 설치한 Visual Studio 워크로드 및 구성 요소에 따라 선택 항목이 다를 수 있습니다. Visual C++ 프로젝트 템플릿이 표시되지 않으면 Visual Studio 설치 관리자를 다시 실행하고 **C++를 사용한 데스크톱 개발** 워크로드를 설치해야 합니다. **새 프로젝트** 대화 상자에서 직접 수행할 수 있습니다. 설치 관리자를 시작하려면 대화 상자에서 **Visual Studio 설치 관리자 열기** 링크를 선택합니다.

1. **확인** 단추를 선택하여 앱 프로젝트 및 솔루션을 만듭니다.

   Windows 콘솔 앱의 기본 파일과 함께 HelloApp 프로젝트 및 솔루션을 만들고 **솔루션 탐색기**에 자동으로 로드합니다. HelloApp.cpp 파일이 코드 편집기에서 열립니다. 다음 항목이 **솔루션 탐색기**에 나타납니다.

   ![솔루션 탐색기의 솔루션 파일](../ide/media/get-started-cpp-solution-explorer.png "솔루션 탐색기의 솔루션 파일")

## <a name="add-code-to-the-app"></a>앱에 코드 추가

다음으로 콘솔 창에 "Hello"를 표시하는 코드를 추가합니다.

### <a name="to-edit-code-in-the-editor"></a>편집기에서 코드를 편집하려면

1. HelloApp.cpp 파일에서 `return 0;` 줄 앞에 빈 줄을 입력하고 다음 코드를 입력합니다.

   ```cpp
   cout << "Hello\n";
   ```

   `cout`아래에 빨간색 물결선이 나타납니다. 그 위로 포인터를 가져가면 오류 메시지가 나타납니다.

   ![cout에 대한 오류 텍스트](../ide/media/get-started-cpp-intellisense-error.png "cout에 대한 오류 텍스트")

   이 오류 메시지는 **오류 목록** 창에도 나타납니다. 메뉴 모음에서 **보기>오류 목록**을 선택하여 이 창을 표시할 수 있습니다.

   ![오류 목록 창의 오류](../ide/media/get-started-cpp-error-list.png "오류 목록 창의 오류")

   코드는 \<iostream > 헤더 파일에서 찾을 수 있는 [std::cout](/cpp/standard-library/iostream)에 대한 선언을 누락했습니다.

1. Iostream 헤더를 포함하려면 `#include "stdafx.h"` 뒤에 다음 코드를 입력합니다.

   ```cpp
   #include <iostream>
   using namespace std;
   ```

   코드를 입력하면 상자가 나타나는 것을 확인할 수 있습니다. 이 상자에는 입력한 문자에 대한 자동 완성 제안이 포함됩니다. 이 기능은 C++ IntelliSense의 일부로, 클래스 또는 인터페이스 멤버 및 매개 변수 정보를 비롯한 코딩 프롬프트를 제공합니다. 또한 미리 정의된 코드 블록인 코드 조각을 사용할 수도 있습니다. 자세한 내용은 [Using IntelliSense](../ide/using-intellisense.md) 및 [Code Snippets](../ide/code-snippets.md)을 참조하세요.

   ![편집기의 고정된 코드](../ide/media/get-started-cpp-cout-fix.png "편집기의 고정된 코드")

   `cout` 아래의 빨간색 물결선은 오류를 해결하면 사라집니다.

1. 파일의 변경 내용을 저장하려면 **Ctrl+S**를 누릅니다.

## <a name="build-the-app"></a>앱 빌드

코드를 작성하는 것이 쉽습니다. 메뉴 모음에서 **빌드 > 솔루션 빌드**를 선택합니다. Visual Studio는 HelloApp 솔루션을 빌드하고 **출력** 창에서 진행률을 보고합니다.

   ![HelloApp 솔루션 빌드](../ide/media/get-started-cpp-build-solution.gif "HelloApp 솔루션 빌드")

## <a name="debug-and-test-the-app"></a>앱 디버그 및 테스트

HelloApp을 디버그하여 단어 "Hello"가 콘솔 창에 표시되는지 여부를 확인할 수 있습니다.

### <a name="to-debug-the-app"></a>앱을 디버깅하려면

1. 디버거를 시작하려면 메뉴 모음에서 **디버그 > 디버깅 시작**을 선택합니다.

   ![디버그 메뉴의 디버깅 시작 명령](../ide/media/get-started-cpp-start-debugging-menu.png "디버그 메뉴의 디버깅 시작 명령")

   디버거가 시작되고 코드가 실행됩니다. 콘솔 창(명령 프롬프트외 비슷한 별도의 창)이 몇 초간 나타나지만 디버거에서 실행이 중지되면 바로 닫힙니다. 텍스트를 보려면 중단점을 설정하여 프로그램 실행을 중지해야 합니다.

### <a name="to-add-a-breakpoint"></a>중단점을 추가하려면

1. 편집기에서 `return 0;` 줄에 커서를 놓습니다. 메뉴 모음에서 **디버그 > 중단점 설정/해제**를 선택합니다. 왼쪽 여백을 클릭하여 중단점을 설정할 수도 있습니다.

     ![디버그 메뉴의 중단점 설정/해제 명령](../ide/media/get-started-cpp-toggle-breakpoint-menu.png "디버그 메뉴의 중단점 설정/해제 명령")

     편집기 창의 맨 왼쪽 여백 코드 줄 옆에 빨간색 원이 나타납니다.

     ![창 여백에 표시된 중단점](../ide/media/get-started-cpp-breakpoint-set.png "창 여백에 표시된 중단점")

1. 디버깅을 시작하려면 **F5** 키를 누릅니다.

   디버거가 시작되고 단어 **Hello**를 표시하는 콘솔 창이 나타납니다.

   ![콘솔 창의 Hello 텍스트](../ide/media/get-started-cpp-helloapp-window.png "콘솔 창의 Hello 텍스트")

1. 디버깅을 중지하려면 **Shift+F5** 키를 누릅니다.

콘솔 프로젝트 디버깅에 대한 자세한 내용은 [콘솔 프로젝트](../debugger/debugging-preparation-console-projects.md)를 참조하세요.

## <a name="build-a-release-version-of-the-app"></a>앱 릴리스 버전 빌드

모든 것이 작동하는 것을 확인했으므로 응용 프로그램의 릴리스 빌드를 준비할 수 있습니다. 릴리스 빌드는 디버깅 정보를 두고 컴파일러 최적화 옵션을 사용하여 더 작고 빠른 코드를 만듭니다.

### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>솔루션 파일을 정리하고 릴리스 버전을 빌드하려면

1. 메뉴 모음에서 **빌드 > 솔루션 정리**를 선택하여 이전 빌드 과정에서 만들어진 중간 파일과 출력 파일을 삭제합니다.

   ![빌드 메뉴의 솔루션 정리 명령](../ide/media/get-started-cpp-clean-solution-menu.png "ExploreIDE-CleanSolution")

1. **디버그**부터 **릴리스**까지 HelloApp에 대한 솔루션 구성을 변경하려면 도구 모음에서 솔루션 구성 컨트롤에 대한 드롭다운을 선택한 다음 **릴리스**를 선택합니다.

   ![응용 프로그램 릴리스 버전 빌드](../ide/media/get-started-cpp-set-release-configuration.png "C++IDE_ChangingBuildtoRelease")

1. 솔루션을 빌드합니다. 메뉴 모음에서 **빌드 > 솔루션 빌드**를 선택합니다.

이 빌드가 완료되면 명령 프롬프트 창에서 복사하고 실행할 수 있는 앱이 만들어집니다. 많은 작업을 수행하지 않지만 더 많은 작업에 대한 게이트웨이입니다.

이 빠른 시작을 완료한 것을 축하 드립니다! 더 많은 예제를 탐색하려는 경우 [Visual Studio 샘플](../ide/visual-studio-samples.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[C++ 데스크톱 개발에 Visual Studio IDE 사용](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)  
[연습: Visual C# 또는 Visual Basic으로 간단한 응용 프로그램 만들기](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)  
[Visual Studio 생산성 팁](../ide/productivity-tips-for-visual-studio.md)  
[Visual Studio 샘플](../ide/visual-studio-samples.md)  
[Visual Studio에서 개발 시작](../ide/get-started-developing-with-visual-studio.md)
