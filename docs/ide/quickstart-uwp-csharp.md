---
title: '빠른 시작: XAML 및 C#을 사용하여 Visual Studio에서 첫 번째 유니버설 Windows 플랫폼 응용 프로그램 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology:
- vs-acquisition
ms.topic: quickstart
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a653dd6488a366f229311c3541c37cf5e984fc99
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>빠른 시작: XAML 및 C&#35를 사용하여 Visual Studio에서 첫 번째 유니버설 Windows 플랫폼 응용 프로그램 만들기

5~10분 분량의 Visual Studio IDE(통합 개발 환경)에 대한 소개에서는 모든 Windows 10 장치에서 실행되는 "Hello World" 앱을 만듭니다. 이렇게 하려면 UWP(유니버설 Windows 플랫폼) 프로젝트 템플릿, XAML(Extensible Application Markup Language) 및 C# 프로그래밍 언어를 사용합니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저, 유니버설 Windows 플랫폼 프로젝트를 만듭니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 차례로 선택합니다.

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual C#** 을 확장하고 **Windows 유니버설**을 선택합니다. 중간 창에서 **빈 앱(유니버설 Windows)** 을 선택합니다. 프로젝트 이름을 *HelloWorld*로 지정하고 **확인**을 선택합니다.

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 Windows 유니버설 프로젝트 템플릿](../ide/media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > **빈 앱(유니버설 Windows)** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다.<br><br>![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크 클릭](../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Visual Studio 설치 관리자가 시작됩니다. **유니버설 Windows 플랫폼 개발** 워크로드를 선택한 다음, **수정**을 선택합니다.<br><br>![Visual Studio 설치 관리자에서 유니버설 Windows 플랫폼 개발 워크로드](../ide/media/uwp-dev-workload.png)

4. **새 유니버설 Windows 플랫폼 프로젝트** 대화 상자가 나타나면 **확인**을 선택합니다.

   ![새 유니버설 Windows 플랫폼 프로젝트 대화 상자에서 기본 대상 버전 및 최소 버전 설정에 동의](../ide/media/new-uwp-project-target-minver-dialog.png)

  > [!NOTE]
  > 처음으로 Visual Studio를 사용하여 UWP 앱을 만든 경우 **설정** 대화 상자가 나타날 수 있습니다. **개발자 모드**를 선택한 다음, **예**를 선택합니다.<br><br>
 ![UWP 설정 대화 상자에서 개발자 모드를 사용하도록 설정](../ide/media/enable-developer-mode.png)<br><br>Visual Studio는 사용자용 추가 개발자 모드 패키지를 설치합니다. 패키지 설치가 완료되면 **설정** 대화 상자를 닫습니다.

## <a name="create-the-application"></a>응용 프로그램 만들기

개발을 시작할 때입니다. 단추 컨트롤을 추가하고 해당 단추에 작업을 추가한 다음, 모양을 확인하려면 "Hello World" 앱을 시작합니다.

### <a name="add-a-button-to-the-design-canvas"></a>디자인 캔버스에 단추 추가

1. **솔루션 탐색기**에서 *MainPage.xaml*을 두 번 클릭하여 분할 보기를 엽니다.

  ![솔루션 탐색기에서 MainPage.xaml 열기 ](../ide/media/uwp-solution-explorer-MainPage-xaml.png)

  디자인 캔버스를 포함하는 **XAML 디자이너** 및 코드를 추가하거나 변경할 수 있는 **XAML 편집기**라는 두 개의 창이 있습니다.    

  ![XAML 편집기의 XAML 디자이너 창](../ide/media/uwp-xaml-editor.png)

2. **도구 상자**를 선택하여 도구 상자 플라이아웃 창을 엽니다.

  ![도구 상자를 클릭하여 도구 상자 플라이아웃 창 열기](../ide/media/uwp-toolbox.png)

  (**도구 상자** 옵션이 표시되지 않으면 메뉴 모음에서 열 수 있습니다. 그러려면 **보기** > **도구 모음**을 선택합니다. 또는 **Ctrl**+**Alt**+**X** 키를 누릅니다.)

3. **Pin** 아이콘을 클릭하여 도구 상자 창을 고정합니다.

  ![Pin 아이콘을 클릭하여 도구 상자 창 고정](../ide/media/uwp-toolbox-autohide.png)

4. **단추** 컨트롤을 클릭해 디자인 캔버스로 끌어옵니다.

   ![단추 컨트롤을 클릭해 디자인 캔버스로 끌어오기](../ide/media/uwp-toolbox-add-button-control.png)

  **XAML 편집기**에 코드가 표시되면 단추가 추가된 것도 확인할 수 있습니다.

  ![단추 컨트롤을 클릭해 디자인 캔버스로 끌어오기](../ide/media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>단추에 레이블 추가

1. **XAML 편집기**에서 단추 콘텐츠 값을 "단추"에서 "Hello World"로 변경합니다!

   ![Hello World로 단추 콘텐츠 값 변경](../ide/media/uwp-change-button-text-in-xaml-code-window.png)

2. **XAML 디자이너**에서도 단추가 변경되는지 확인합니다.

   ![단추가 디자인 캔버스에서 Hello World로 변경됨](../ide/media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>이벤트 처리기 추가

"이벤트 처리기"는 복잡해 보이지만 이벤트가 발생할 때 호출되는 코드에 대한 다른 이름에 지나지 않습니다. 이 경우 "Hello World"에 작업을 추가합니다! 클릭합니다.

1. 디자인 캔버스에서 단추 컨트롤을 두 번 클릭합니다.

2. 코드 숨김 페이지, *MainPage.xaml.cs*에서 이벤트 처리기 코드를 편집합니다.

 지금부터가 흥미로운 부분입니다. 기본 이벤트 처리기는 다음과 같습니다.

   ![기본 Button_Click 이벤트 처리기 ](../ide/media/uwp-button-click-code.png)

 다음과 같이 되도록 바꿔보겠습니다.

    ![새 비동기 Button_Click 이벤트 처리기 ](../ide/media/uwp-add-hello-world-async-code.png)

  복사 및 붙여넣기할 코드는 다음과 같습니다.

  ```C#
  private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
  ```

#### <a name="what-did-we-just-do"></a>무엇을 했습니까?

코드는 일부 Windows API를 사용하여 음성 합성 개체를 만든 다음, 텍스트를 제공하여 읽게 합니다. (`SpeechSynthesis`을 사용하는 방법에 대한 자세한 내용은 <xref:System.Speech.Synthesis>를 참하세요.)

## <a name="run-the-application"></a>응용 프로그램 실행

"Hello World" UWP 앱을 빌드하고 배포하고 시작하여 모양과 음성을 확인할 때입니다. 방법은 다음과 같습니다.

1. **로컬 컴퓨터**를 선택하여 응용 프로그램을 시작합니다.

   ![UWP 앱을 시작하고 디버그하려면 로컬 컴퓨터 클릭](../ide/media/uwp-start-or-debug.png "UWP 앱을 시작하고 디버그하려면 로컬 컴퓨터 클릭")

   (또는 앱을 시작하려면 메뉴 모음에서 **디버그** > **디버깅 시작**을 선택하거나 **F5** 키를 누릅니다.)

2. 시작 화면이 사라진 직후 나타나는 앱을 봅니다. 앱은 다음과 같아야 합니다.

   ![UWP "Hello World" 앱](../ide/media/uwp-hello-world-app.png)

3. **Hello World** 단추를 클릭합니다.

 Windows 10 장치는 말 그대로 "Hello, World!"라고 말합니다.

4. 앱을 닫으려면 도구 모음에서 **디버깅 중지** 단추를 클릭합니다. (또는 메뉴 모음에서 **디버그** > **디버깅 중지**를 선택하거나 **Shift**+**F5** 키를 누릅니다.)

## <a name="next-steps"></a>다음 단계

이 빠른 시작을 완료한 것을 축하 드립니다! UWP 및 Visual Studio IDE에 대한 몇 가지 기본 사항을 알게 됐기를 바랍니다. 자세히 알아보려면 계속 다음 자습서를 사용하세요.

> [!div class="nextstepaction"]
> [사용자 인터페이스 만들기](/windows/uwp/design/basics/xaml-basics-ui)
