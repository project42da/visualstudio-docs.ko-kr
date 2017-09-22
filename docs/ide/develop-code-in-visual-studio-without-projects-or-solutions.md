---
title: "프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발 | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.texteditor
dev_langs:
- JScript
- VB
- CSharp
helpviewer_keywords:
- code, editing
- code editor, syntax coloring
- code editor [Visual Studio]
- brace matching
- code editor, line numbers
- code editor, brace matching
- line numbers
- syntax coloring
- code editor
- code files
- code
ms.assetid: cb53bb9b-5b76-4759-b9b8-7bf32298bcbb
caps.latest.revision: 44
author: gewarren
ms.author: gewarren
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 3a8be04b4d2c927dc296753420ff736b993343c9
ms.contentlocale: ko-kr
ms.lasthandoff: 03/07/2017

---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발

Visual Studio 2017에서는 솔루션이나 프로젝트 파일 없이 거의 모든 유형의 디렉터리 기반 프로젝트에서 Visual Studio로 코드를 열 수 있습니다. 예를 들어 Git에서 코드 프로젝트를 찾고 복제한 다음 Visual Studio로 직접 열고, 솔루션이나 프로젝트를 만들지 않고도 개발을 시작할 수 있습니다.

Visual Studio에서 코드를 편집하고 빌드할 수 있을 뿐만 아니라 코드를 탐색할 수도 있습니다(예: [다음 탐색] 명령). 코드는 구문 색 지정으로 표시되며, 대부분의 경우 기본 문 완성, 디버깅, 중단점 완성을 포함합니다. 일부 언어에는 더 많은 기능이 포함됩니다. 자세한 내용은 [휴대용, 사용자 지정 편집기 설정 만들기](create-portable-custom-editor-options.md)를 참조하세요.

## <a name="open-code-anywhere"></a>어디서나 코드 열기
Visual Studio에서 다음과 같은 방법으로 코드를 열 수 있습니다.
- Visual Studio 메뉴 모음에서 **파일**, **열기**, **폴더**를 차례로 선택한 다음 코드 위치를 찾습니다.
- 코드가 포함된 폴더의 상황에 맞는 메뉴(마우스 오른쪽 단추 클릭)에서 **Visual Studio에서 열기** 명령을 선택합니다.
- Visual Studio 시작 페이지에서 **폴더 열기** 링크를 선택합니다.
- GitHub 리포지토리에서 복제된 코드를 엽니다.

다음 예제에서는 GitHub 리포지토리를 복제한 다음 Visual Studio에서 해당 코드를 여는 방법을 보여 줍니다. 이 절차를 따르려면 GitHub 계정이 있어야 하고, 시스템에 Git for Windows가 설치되어 있어야 합니다. 자세한 내용은 [새 GitHub 계정 등록](https://help.github.com/articles/signing-up-for-a-new-github-account/)(영문) 및 [Git for Windows](https://git-for-windows.github.io/)(영문)를 참조하세요.

### <a name="to-open-code-from-a-cloned-github-repo"></a>복제된 GitHub 리포지토리에서 코드를 열려면

1. 작업하려는 코드가 있는 GitHub 리포지토리로 이동합니다. 이렇게 하려면 GitHub 계정이 있어야 합니다.
1. 복제하려는 리포지토리로 이동합니다.
1. 리포지토리의 GitHub 페이지에서 **복제 또는 다운로드** 단추를 선택한 다음, 드롭다운 메뉴에서 **클립보드로 복사** 단추를 선택하여 GitHub 사이트에 대한 보안 URL을 복사합니다.

  ![GitHub 복제 단추](./media/VSIDE_Code_Clone.png)

    > [!NOTE]
    >  데스크톱에서 프로젝트를 열거나 프로젝트의 .zip 파일을 다운로드하는 옵션도 있지만, 이 예제에서는 보안 URL 메서드를 사용하여 리포지토리를 복제하는 방법을 보여 줍니다.

1. Visual Studio에서 **팀 탐색기** 탭을 선택하여 [팀 탐색기]를 엽니다.
1. [팀 탐색기]의 **로컬 Git 리포지토리** 섹션에서 **복제** 명령을 선택한 다음, GitHub 페이지의 URL을 텍스트 상자에 붙여넣습니다.

  ![프로젝트 복제](./media/VSIDE_Code_Clone2.png)

1. **복제** 단추를 선택하여 프로젝트 파일을 로컬 Git 리포지토리에 복제합니다. 리포지토리의 크기에 따라 이 프로세스에는 몇 분이 걸릴 수 있습니다.
1. 시스템에 리포지토리를 복제한 후에 [팀 탐색기]에서 새로 복제된 프로젝트의 상황에 맞는 메뉴(마우스 오른쪽 단추 클릭)에서 **열기** 명령을 선택합니다.

  ![복제된 프로젝트](./media/VSIDE_Code_Clone3.png)

1. **폴더 보기 표시** 명령을 선택하여 [솔루션 탐색기]에서 파일을 봅니다.

  ![폴더 보기 표시](./media/VSIDE_Code_Clone3_show.png)

  이제 복제된 프로젝트의 폴더와 파일을 탐색하고, Visual Studio 코드 편집기에서 구문 색 지정 및 기타 기능을 사용하여 완성된 코드를 보고 검색할 수 있습니다.

    ![복제된 프로젝트 코드 검색](./media/VSIDE_Code_Clone4.png)


## <a name="debug-your-code"></a>코드 디버그
Visual Studio에서 코드를 디버그할 수 있습니다. 일부 언어를 디버그하려면 스크립트, 실행 파일 또는 프로젝트와 같은 유효한 *시작 파일*을 코드 프로젝트에 지정해야 할 수 있습니다. 코드를 디버그할 때는 먼저 지정된 해당 코드를 Visual Studio에서 실행합니다.

도구 모음의 [시작] 단추 옆에 있는 드롭다운 목록 상자에서는 Visual Studio에서 검색한 모든 시작 항목과 폴더에서 특별히 선택한 항목을 나열합니다.

![실행 단추](./media/VSIDE_Code_Run_Button.png)

Visual Studio는 프로젝트를 자동으로 인식하지만, 목록에 표시되기 전에 스크립트(예: Python 및 JavaScript)를 시작 항목으로 명시적으로 선택해야 합니다.
또한 MSBuild 및 CMake와 같은 일부 시작 항목에는 실행 단추의 드롭다운 목록에 표시되는 여러 개의 빌드 구성이 있을 수 있습니다.

Visual Studio는 현재 다음 언어에 대한 디버깅을 지원하고 있습니다.
- Node.js
- Python
- MSBuild 기반 프로젝트(C#, VB, C++)
- PDB(Python 디버거) 파일을 가진 모든 실행 파일

### <a name="to-debug-nodejs-and-python"></a>Node.js와 Python을 디버그하려면
1. Node.js 또는 Visual Studio 2017용 Python 도구 및 Node.js 런타임을 설치합니다.
1. [솔루션 탐색기]의 JavaScript 파일의 상황에 맞는 메뉴에서 **시작 항목으로 설정** 명령을 선택합니다.
1. F5 키를 선택하여 디버깅을 시작합니다.

### <a name="to-debug-msbuild-projects"></a>MSBuild 프로젝트를 디버그하려면
1. Visual Studio 메뉴에서 **디버그**를 선택합니다. 드롭다운 메뉴에서 프로젝트를 선택하거나 [솔루션 탐색기]에서 시작 항목으로 표시할 프로젝트 또는 파일을 선택합니다.
1. F5 키를 선택하여 디버깅을 시작합니다.

### <a name="to-debug-executable-files"></a>실행 파일을 디버그하려면
1. Visual Studio 메뉴에서 **디버그**를 선택합니다. 드롭다운 메뉴에서 프로젝트를 선택하거나 [솔루션 탐색기]에서 시작 항목으로 표시할 프로젝트 또는 파일을 선택합니다.
1. F5 키를 선택하여 디버깅을 시작합니다.


## <a name="enable-custom-build-tools"></a>사용자 지정 빌드 도구를 사용하도록 설정
Visual Studio는 여러 다른 언어를 실행하는 방법을 알고 있지만, 모든 언어를 실행하는 방법은 알고 있지 않습니다. Visual Studio에서 언어를 실행하는 방법을 알고 있는 경우 코드를 바로 실행할 수 있습니다. 코드를 실행하려고 하지만 Visual Studio에서 실행 방법을 모르는 경우 코드베이스의 파일을 시작 항목으로 작동하도록 지정하라는 메시지가 알림 표시줄에 표시됩니다.

하지만 코드베이스가 Visual Studio에서 인식하지 못하는 사용자 지정 빌드 도구를 사용하는 경우 언어에 필요한 모든 사용자 지정 매개 변수 및 인수와 함께 유효한 실행 파일 형식(예: 컴파일러)을 지정할 때까지 Visual Studio에서 코드를 실행하고 디버그할 수 없습니다(예 : F5 키 선택). 이 기능을 사용하도록 설정하기 위해 Visual Studio에서 *빌드 작업*을 제공합니다. 코드를 빌드하고 실행할 수 있도록 언어에 필요한 모든 항목을 지정하는 빌드 작업을 만들 수 있습니다.

또한 원하는 거의 모든 작업을 수행할 수 있는 임의의 빌드 작업을 만들 수도 있습니다. 예를 들어 폴더의 내용을 나열하거나 파일의 이름을 바꾸는 작업을 만들 수 있습니다. 또는 더 많은 대상이 지정된 사용자 지정 빌드 작업을 만들어 컴파일과 같은 작업을 수행하고 특정 인수를 사용하여 프로젝트를 빌드할 수 있습니다. 다음 단계에서는 두 유형의 빌드 작업을 만드는 방법을 보여 줍니다.

#### <a name="to-create-an-arbitrary-build-task"></a>임의의 빌드 작업을 만들려면

1. [솔루션 탐색기]에서 작업이 필요한 프로젝트의 파일이나 폴더를 선택하고, 해당 파일이나 폴더의 상황에 맞는 메뉴(마우스 오른쪽 단추 클릭)에서 **작업 구성**을 선택합니다.

  ![작업 구성](./media/VSIDE_Code_Config_Task.png)

  **작업 구성**을 선택하면 tasks.vs.json이라는 파일이 열립니다. 이 파일이 없으면 해당 파일이 만들어집니다. 이 파일에는 선택한 파일이나 폴더의 빌드 작업이 포함되어 있습니다.

  ![Tasks.vs.json 파일](./media/VSIDE_Code_Tasks_JSON.png)

1. tasks.vs.json에 다음 빌드 작업을 추가합니다. 이 예제에서는 [출력] 창에 선택한 폴더의 파일과 하위 폴더를 나열하는 "출력 나열"이라는 간단한 작업을 추가합니다. 새 작업은 기존 "작업" 배열에 추가되어야 합니다.

  ```xml
      {
        "taskName": "List outputs",
        "appliesTo": "*",
        "type": "command",
        "command": "${env.COMSPEC}",
        "args": [
          "dir ${outDir}"
        ]
      },
  ```
  전체 빌드 작업은 다음과 같이 표시됩니다.

  ![임의의 빌드 작업](./media/VSIDE_Code_Tasks_ArbTask.png)

1. 프로젝트를 저장합니다.
1. 선택한 폴더의 상황에 맞는 메뉴를 엽니다. 상황에 맞는 메뉴의 아래쪽에 새로운 임의의 빌드 작업이 표시되어야 합니다.

  ![임의의 빌드 작업 명령](./media/VSIDE_Code_Tasks_ArbTask2.png)

1. 새로운 **출력 나열** 명령을 선택하여 해당 작업을 실행합니다.


### <a name="to-create-a-custom-build-task"></a>사용자 지정 빌드 작업을 만들려면
이 절차에서는 nMake를 사용하여 코드를 빌드하고 정리하는 두 가지 사용자 지정 빌드 작업을 추가합니다.

1. [솔루션 탐색기]에서 나중에 시작 항목으로 지정할 프로젝트 파일을 선택합니다. 파일의 상황에 맞는 메뉴(마우스 오른쪽 단추 클릭)에서 **작업 구성**을 선택합니다.

  ![사용자 지정 빌드 작업 명령](./media/VSIDE_Code_Tasks_CustTask1.png)

1. tasks.vs.json에 다음 빌드 작업을 추가합니다. 이 예제에서는 두 가지 작업, 즉 nMake 명령을 사용하여 프로젝트를 빌드하는 "makefile-build" 작업과 "clean" 인수로 nMake 명령을 호출하는 "makefile-clean" 작업을 추가합니다. 이러한 작업은 기존 "작업" 배열 내에 추가되어야 합니다. (이는 예제 빌드 작업일 뿐입니다. 실제로 작동하려면 시스템에 [nNake](https://docs.microsoft.com/en-us/cpp/build/nmake-reference)가 설치되어 있는 작업이 있어야 합니다.)

  ```xml
  {
  "taskName": "makefile-build",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "build",
  "command": "nmake"
  },
  {
  "taskName": "makefile-clean",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "clean",
  "command": "nmake",
  "args": [
    "clean"
    ]
  },
  ```
  전체 사용자 지정 빌드 작업은 다음과 같이 표시됩니다.

  ![사용자 지정 빌드 작업](./media/VSIDE_Code_Tasks_CustTask2.png)

1. 프로젝트를 저장합니다.
1. 선택한 파일의 상황에 맞는 메뉴를 엽니다. 새 사용자 지정 빌드 작업은 상황에 맞는 메뉴의 중간에 표시되어야 합니다.

  ![사용자 지정 빌드 작업 명령](./media/VSIDE_Code_Tasks_CustTask3.png)

  > [!NOTE]
  > 이 명령은 `contextType` 설정으로 인해 **작업 구성** 명령 아래에 표시됩니다. "build" 및 "clean"은 빌드 명령이므로 상황에 맞는 메뉴의 중간에 있는 빌드 섹션에 표시됩니다.

  사용자 지정 빌드 명령과 파일을 연결했으므로 해당 파일을 시작 항목으로 지정할 수 있습니다.

1. 파일의 상황에 맞는 메뉴에서 **시작 항목으로 설정**을 선택합니다.

  ![사용자 지정 빌드 작업 명령](./media/VSIDE_Code_Tasks_CustTask4.png)

1. 도구 모음에서 [시작] 단추 옆에 있는 드롭다운 화살표를 선택합니다. 이제 시작 항목이 옵션으로 표시됩니다.

  ![사용자 지정 빌드 작업 명령](./media/VSIDE_Code_Tasks_CustTask5.png)

이제 [시작] 단추 또는 F5 키를 선택하여 코드베이스를 실행할 수 있습니다. Visual Studio에서 코드베이스의 빌드 도구를 인식하지 못하더라도 Visual Studio에서 코드베이스를 편집하고 디버그할 수 있습니다. 빌드 작업의 출력은 **출력** 창에 표시되고, 빌드 오류는 **오류 목록**에 표시됩니다. tasks.vs.json 빌드 작업 파일은 Visual Studio 내부 개발 루프를 코드베이스에서 사용하는 사용자 지정 빌드 도구에 연결합니다.

사용자 지정 빌드 작업을 개별 파일이나 특정 형식의 모든 파일에 추가할 수 있습니다. 예를 들어 "패키지 복원" 작업을 포함하도록 NuGet 패키지 파일을 구성하거나, 모든 .js 파일에 대해 linter와 같은 정적 분석 작업을 포함하도록 모든 원본 파일을 구성할 수 있습니다.

Visual Studio는 환경 변수(예: `$env.var`) 또는 키 외에도 tasks.vs.json의 루트에서 `$variable` VSCode 대체를 지원합니다.

## <a name="specify-build-output"></a>빌드 출력 지정
프로젝트를 컴파일해야 하는 경우 tasks.vs.json 파일에 `output`이라는 추가 태그를 추가할 수 있습니다. 예를 들면 다음과 같습니다.

`"output": "${workspaceRoot}\\bin\\hellomake.exe"`

출력 위치를 지정하면 프로젝트의 빌드 출력을 찾을 위치를 Visual Studio에 알립니다.


## <a name="tasksvsjson-file-location"></a>Tasks.vs.json 파일 위치

기본적으로 tasks.vs.json 파일은 `.vs`라는 숨겨진 폴더에 있습니다. Visual Studio에서 숨겨진 파일을 보려면 [솔루션 탐색기] 도구 모음에서 **모든 파일 표시** 단추를 선택합니다.

![임의의 빌드 작업 명령](./media/VSIDE_Code_Tasks_FileLocation.png)

대부분의 사용자가 일반적으로 원본 제어로 확인하지 않으므로 tasks.vs.json 파일은 숨겨져 있습니다. 그러나 원본 제어로 확인할 수 있게 하려면 파일을 프로젝트의 루트로 끌어갑니다.

다른 .json 파일은 .vs 폴더에 있을 수 있지만, 이동해야 하는 파일은 tasks.vs.json 파일과 launch.vs.json 파일(있는 경우)뿐입니다. launch.vs.json 파일은 Visual Studio 디버거를 구성하는 반면, tasks.vs.json 파일은 Visual Studio에서 빌드를 구성합니다.

