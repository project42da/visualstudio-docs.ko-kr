---
title: Visual Studio에서 Visual Basic을 사용하여 Windows Forms 앱 만들기
description: Visual Studio에서 Visual Basic을 사용하여 Windows Forms 앱을 만드는 방법을 단계별로 알아봅니다.
ms.custom: ''
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 603fe9c8aaa328e0ae1b42f385a0f8f2b5867955
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="create-a-windows-forms-app-in-visual-studio-with-visual-basic"></a>Visual Studio에서 Visual Basic을 사용하여 Windows Forms 앱 만들기

Visual Studio IDE(통합 개발 환경)에 대한 이 짧은 소개에서는 Windows 기반 UI(사용자 인터페이스)가 있는 간단한 Visual Basic 응용 프로그램을 만듭니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저 Visual Basic 응용 프로그램 프로젝트를 만들어야 합니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...** 를 차례로 선택합니다.

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Basic**을 확장한 후 **Windows 클래식 바탕화면**을 선택합니다. 가운데 창에서 **Windows Forms 앱(.NET Framework)** 을 선택합니다. 그런 다음 파일 이름을 `HelloWorld`로 지정합니다.

     **Windows Forms 앱(.NET Framework)** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자를 취소하고 나가 메뉴 모음에서 **도구** > **도구 및 기능 가져오기...** 를 선택합니다. Visual Studio 설치 관리자가 시작됩니다. **.NET 데스크톱 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

     ![Visual Studio 설치 관리자의 .NET Core 워크로드](../ide/media/install-dot-net-desktop-env.png)

## <a name="create-the-application"></a>응용 프로그램 만들기

Visual Basic 프로젝트 템플릿을 선택하고 파일 이름을 지정한 후에 Visual Studio에서는 양식을 엽니다. 양식은 Windows 사용자 인터페이스입니다. 양식에 컨트롤을 추가하여 "Hello World" 응용 프로그램을 만들고 응용 프로그램 실행합니다.

### <a name="add-a-button-to-the-form"></a>양식에 단추 추가

1. **도구 상자**를 클릭하여 도구 상자 플라이아웃 창을 엽니다.

     ![도구 상자를 클릭하여 도구 상자 창을 엽니다.](../ide/media/vb-toolbox-toolwindow.png)

     (**도구 상자** 플라이아웃 옵션이 표시되지 않으면 메뉴 모음에서 열 수 있습니다. 이렇게 하려면 **보기** > **도구 상자**를 클릭합니다. 또는 **Ctrl**+**Alt**+**X** 키를 누릅니다.)

2. **Pin** 아이콘을 클릭하여 **도구 상자** 창을 고정합니다.

     ![Pin 아이콘을 클릭하여 도구 상자 창을 IDE에 고정합니다.](../ide/media/vb-pin-the-toolbox-window.png)
3. **단추** 컨트롤을 클릭하고 다음 양식으로 끌어옵니다.

     ![양식에 단추 추가](../ide/media/vb-add-a-button-to-form1.png)

4. **속성** 창의 **모양** 섹션에서 `Click this`을 입력한 다음, **Enter** 키를 누릅니다.

     ![폼에서 단추에 텍스트 추가](../ide/media/vb-button-control-text.png)

     (**속성** 창이 표시되지 않으면 메뉴 모음에서 열 수 있습니다. 이렇게 하려면 **보기** > **속성 창**을 클릭합니다. 또는 **F4** 키를 누릅니다.)

5. **속성** 창의 **디자인** 섹션에서 이름을 **Button1**에서 `btnClickThis`로 변경한 다음, **Enter** 키를 누릅니다.

     ![양식에서 단추에 함수 추가](../ide/media/vb-button-control-function.png)

### <a name="add-a-label-to-the-form"></a>양식에 레이블 추가

동작을 만드는 단추 컨트롤을 추가했습니다. 텍스트를 보낼 레이블 컨트롤을 추가해 보겠습니다.

1. **도구 상자** 창에서 **레이블** 컨트롤을 선택한 다음, 양식으로 끌어오고, **항목 클릭** 단추 아래에 놓습니다.

2. **속성** 창의 **디자인** 섹션에서 이름을 **Label1**에서 `lblHelloWorld`로 변경한 다음, **Enter** 키를 누릅니다.

### <a name="add-code-to-the-form"></a>양식에 코드 추가

1. **Form1.vb &#91;Design&#93;** 창에서 **항목 클릭** 버튼을 두 번 클릭하여 **Form1.vb** 창을 엽니다.

      (또는 **솔루션 탐색기** 창에서 **Form1.vb**를 확장한 다음 **Form1**을 클릭할 수 있습니다.)

2. **Form1.vb** 창에서 **Private Sub** 줄과 **End Sub** 줄 간에 `lblHelloWorld.Text = "Hello World!"`를 입력하거나 붙여넣습니다.

     ![양식에 코드 추가](../ide/media/vb-add-code-to-the-form.png)

## <a name="run-the-application"></a>응용 프로그램 실행

1. **시작** 단추를 클릭하여 응용 프로그램을 실행합니다.

     ![시작을 클릭하여 앱을 디버깅하고 실행합니다.](../ide/media/vb-click-start-hello-world.png)

   몇 가지 현상이 발생합니다. Visual Studio IDE에서 **진단 도구** 창이 열리고 **출력** 창도 열립니다. 하지만 IDE 외부에서 **Form1** 대화 상자가 나타납니다. **항목 클릭** 단추 및 **Label1**이라는 텍스트가 포함됩니다.

2. **Form1** 대화 상자에서 **항목 클릭** 단추를 클릭합니다. **Label1** 텍스트를 **Hello World!** 로 변경합니다.

    ![Label1 텍스트를 포함하는 Form1 대화 상자 ](../ide/media/vb-form1-dialog-hello-world.png)

이 빠른 시작을 완료한 것을 축하 드립니다! Visual Basic 및 Visual Studio IDE를 이해하는 데 도움이 되었기를 바랍니다. 보다 자세히 알아보려면 목차에서 **자습서** 섹션에 있는 자습서를 읽어보세요.

## <a name="see-also"></a>참고 항목

* [빠른 시작: Visual Studio에서 Visual Basic을 사용하여 콘솔 앱 만들기](quickstart-visual-basic-console.md)
* [Visual Basic IntelliSense에 대한 자세한 내용](visual-basic-specific-intellisense.md)
