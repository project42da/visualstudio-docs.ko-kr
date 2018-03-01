---
title: "Visual Studio에서 C# 및 ASP.NET Core 시작 | Microsoft Docs"
ms.custom: 
ms.date: 12/11/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: c4d67a57063854f859a766068084d63902ba038e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-c-and-aspnet-in-visual-studio"></a>Visual Studio에서 C# 및 ASP.NET 시작
Visual Studio를 사용하여 ASP.NET Core로 C#을 개발하기 위한 이 자습서에서는 C# ASP.NET Core 웹앱을 만들고, 해당 앱에 코드를 추가하며, IDE의 일부 기능을 살펴보고 앱을 실행합니다. 

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="before-you-begin"></a>시작하기 전에
다음은 몇 가지 주요 개념을 소개하는 빠른 FAQ입니다.
### <a name="what-is-c"></a>C#이란?
[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)은 강력하면서도 쉽게 배울 수 있게 설계된 형식이 안전한 개체 지향 프로그래밍 언어입니다.
### <a name="what-is-aspnet-core"></a>ASP.NET Core란? 
ASP.NET Core는 웹앱 및 서비스처럼 인터넷으로 연결된 응용 프로그램을 빌드하기 위한 오픈 소스의 플랫폼 간 프레임워크입니다. ASP.NET Core 앱은 .NET Framework 또는.NET Core에서 실행할 수 있습니다. Windows, Mac 및 Linux에서 ASP.NET Core 앱을 플랫폼 간에 개발하여 실행할 수 있습니다. ASP.NET Core는 [GitHub](https://github.com/aspnet/home)에서 오픈 소스로 제공됩니다.
### <a name="what-is-visual-studio"></a>Visual Studio란?
Visual Studio는 개발자를 위한 통합 개발 생산성 도구입니다. 프로그램과 응용 프로그램을 만드는 데 사용할 수 있는 프로그램으로 생각하면 됩니다.  

## <a name="start-developing"></a>개발 시작
개발을 시작할 준비가 되셨나요? 이제 시작해 보겠습니다.

### <a name="create-a-project"></a>프로젝트 만들기
먼저 ASP.NET Core 프로젝트를 만들 것입니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...**를 차례로 선택합니다.

3. 왼쪽 창의 **새 프로젝트** 대화 상자에서 **Visual C#**, **Web**을 차례로 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **ASP.NET Core 웹 응용 프로그램**을 선택하고 파일 이름을 *MyCoreApp*으로 정한 다음 **확인**을 선택합니다.   

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 ASP.NET Core 웹 응용 프로그램 프로젝트 템플릿](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>(선택 사항) 워크로드 추가
**ASP.NET Core 웹 응용 프로그램** 프로젝트 템플릿이 표시되지 않는 경우, **ASP.NET 및 웹 개발** 워크로드를 추가하여 얻을 수 있습니다. 컴퓨터에 Visual Studio 2017 업데이트가 설치되었는지 여부에 따라 다음 두 방법 중 하나로 이 워크로드를 추가할 수 있습니다.

##### <a name="option-1-use-the-new-project-dialog-box"></a>옵션 1: 새 프로젝트 대화 상자 사용
1. **새 프로젝트** 대화 상자에서 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다.

  ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크를 클릭합니다.](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

   ![Visual Studio Installer에서 .NET Core 플랫폼 간 개발 워크로드](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>옵션 2: 도구 메뉴 모음 사용
1. **새 프로젝트** 대화 상자를 취소하고 나가 상단 메뉴 모음에서 **도구** > **도구 및 기능 가져오기...**를 선택합니다.

2. Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.   

#### <a name="add-a-project-template"></a>프로젝트 템플릿 추가
1. **새 ASP.NET Core 웹 응용 프로그램** 대화 상자에서 **웹 응용 프로그램모델-뷰-컨트롤러)** 프로젝트 템플릿을 선택합니다.  

2. 상단 드롭다운 메뉴에서 **ASP.NET Core 2.0**을 선택합니다. (목록에 **ASP.NET Core 2.0**이 표시되지 않으면 대화 상자 맨 위에 있는 노란색 표시줄에 나타나는 **다운로드** 링크에 따라 설치합니다.) **확인**을 선택합니다.

   ![새 ASP.NET Core 웹 응용 프로그램 대화 상자](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>솔루션 정보
이 솔루션은 앱을 다음과 같이 세 가지 주요 구성 요소로 구분하는 MVC(모델-뷰-컨트롤러) 아키텍처 패턴을 따릅니다. 

* **M(모델)**은 앱 데이터를 나타내는 클래스를 포함합니다. 모델 클래스는 유효성 검사 논리를 사용하여 해당 데이터의 비즈니스 규칙을 적용합니다. 일반적으로 모델 개체는 모델 상태를 검색하고 데이터베이스에 저장합니다.
* **V(뷰)**는 앱의 UI(사용자 인터페이스)를 표시하는 구성 요소입니다. 일반적으로 이 UI는 모델 데이터를 표시합니다.
* **C(컨트롤러)**는 브라우저 요청을 처리하는 클래스를 포함합니다. 모델 데이터를 검색하고 응답을 반환하는 뷰 템플릿을 호출합니다. MVC 앱에서 뷰는 정보만 표시합니다. 즉 컨트롤러가 사용자 입력 및 상호 작용을 처리하고 응답합니다.

MVC 패턴을 통해 기존 모놀리식 응용 프로그램보다 테스트 및 업데이트가 용이한 앱을 만들 수 있습니다.

### <a name="tour-your-solution"></a>솔루션 둘러보기
1. 프로젝트 템플릿은 **MyCoreApp**이라는 단일 ASP.NET Core 프로젝트와 솔루션을 만듭니다. 프로젝트 노드를 확장하면 그 안의 콘텐츠가 표시됩니다.

    ![Visual Studio의 ASP.NET 솔루션 탐색기](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

1. **컨트롤러** 폴더에서 **HomeController.cs** 파일을 엽니다.

      ![Visual Studio 솔루션 탐색기의 HomeController.cs 파일](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

2. **HomeController.cs** 보기

  ![Visual Studio 코드 창의 HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

4. 이 프로젝트에는 각 컨트롤러에 매핑되는 다른 폴더를 포함하는 **Views** 폴더도 있습니다(**Shared** 뷰에 대한 폴더 1개 포함). 예를 들어 **/Home/About** 경로에 대한 뷰 CSHTML 파일(HTML 확장)은 **Views/Home/About.cshtml**에 있습니다. 해당 파일을 엽니다.

  ![Visual Studio 솔루션 탐색기의 About.cshtml 파일](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

5. 이 CSHTML 파일은 표준 태그와 인라인 C# 조합을 기준으로 HTML을 렌더링하기 위해 Razor 구문을 사용합니다.

  ![Visual Studio 코드 창의 About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

 >[!NOTE]
 > 이에 대한 자세한 내용은 [Razor 구문을 사용하여 C# 및 ASP.NET 시작](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) 페이지를 참조하세요.

6. 솔루션에는 웹 사이트의 루트인 **wwwroot** 폴더도 포함됩니다. CSS, 이미지 및 JavaScript 라이브러리 같은 정적 사이트 콘텐츠를 사이트 배포 시점에 놓으려는 경로에 직접 배치할 수 있습니다.

 ![Visual Studio 솔루션 탐색기의 wwwroot 폴더](../ide/media/csharp-aspnet-solution-wwwroot.png)

7. 런타임 시 프로젝트, 그 패키지 및 응용 프로그램의 관리를 지원하는 다양한 구성 파일도 있습니다. 예를 들어 기본 응용 프로그램 [구성](/aspnet/core/fundamentals/configuration)은 **appsettings.json**에 저장됩니다. 그러나 **Development** 환경에 대해 **appsettings.Development.json** 파일을 제공하는 등의 방식으로 환경을 기준으로 이 설정의 일부/전체를 재정의할 수 있습니다.

 ![Visual Studio 솔루션 탐색기의 구성 파일](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>응용 프로그램 실행 및 디버그

1. IDE에서 **IIS Express** 단추를 선택하여 디버그 모드에서 앱을 빌드 및 실행합니다. 또는 **F5**를 누르거나 메뉴 모음에서 **디버그 > 디버깅 시작**을 선택합니다.

  ![Visual Studio에서 IIS Express 단추 클릭](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > **'IIS Express' 웹 서버에 연결할 수 없습니다**라는 오류 메시지가 발생하면 Visual Studio를 닫은 후 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 **관리자 권한으로 실행** 옵션을 사용하여 엽니다. 그런 다음 응용 프로그램을 다시 실행합니다.

1. Visual Studio가 브라우저 창을 시작합니다. **About**을 선택합니다.

 ![앱의 브라우저 창에서 About 선택](../ide/media/csharp-aspnet-browser-page.png)

 무엇보다 브라우저의 About 페이지는 HomeController.cs 파일에서 설정된 텍스트를 렌더링합니다.

   ![About 페이지에서 텍스트 보기](../ide/media/csharp-aspnet-browser-page-about.png)

1. 브라우저 창을 열어둔 상태에서 Visual Studio로 돌아갑니다. 아직 열려 있지 않으면 **Controllers/HomeController.cs**를 엽니다.

 ![Visual Studio 솔루션 탐색기에서 HomeController.cs 파일 열기](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

1. **About** 메서드의 첫 줄에 중단점을 설정합니다. 이를 위해 여백을 클릭하거나 줄에 커서를 두고 **F9**를 누릅니다.

  이 줄은 **Views/Home/About.cshtml**의 CSHTML 페이지에서 렌더링되는 **ViewData** 컬렉션에 일부 데이터를 설정합니다.

 ![About.cshtml에서 About 메서드의 첫 줄에 중단점을 설정합니다.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

1. 브라우저로 돌아가 About 페이지를 새로 고칩니다. 이렇게 하면 Visual Studio에서 중단점이 트리거됩니다.

1. Visual Studio에서 **ViewData** 멤버 위에 마우스를 가져가 데이터를 확인합니다.

 ![자세한 정보를 보기 위해 About 메서드의 ViewData 멤버 보기](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

1. 중단점을 추가하는 데 사용한 것과 같은 방법으로 응용 프로그램 중단점을 제거합니다.

1. **Views/Home/About.cshtml**을 엽니다.

 ![솔루션 탐색기에서 About.cshtml 선택](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

1. **"additional"** 텍스트를 **"changed"**으로 변경하여 파일을 저장합니다.

 !["additional" 텍스트를 "changed"로 표시되게 변경](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

1. 브라우저 창으로 돌아가 업데이트된 텍스트를 확인합니다. 변경한 텍스트가 표시되지 않으면 브라우저를 새로 고칩니다.

  ![브라우저 창을 새로 고쳐 변경된 텍스트 확인](../ide/media/csharp-aspnet-browser-page-about-changed.png)

1. 도구 모음에서 **디버깅 중지** 단추를 선택하여 디버깅을 중지합니다. 또는 **Shift**+**F5**를 누르거나 메뉴 모음에서 **디버그** > **디버깅 중지**를 선택합니다.

 ![도구 모음에서 디버깅 중지 단추 클릭](../ide/media/csharp-aspnet-stop-debugging.png)


축하합니다. 이 자습서를 마쳤습니다.

## <a name="see-also"></a>참고 항목
* [ASP.NET Core MVC 및 Visual Studio 시작](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x)
* [ASP.NET Core에서 Razor 페이지 시작](/aspnet/core/tutorials/razor-pages/razor-pages-start)
* [C#의 새로운 기능](/dotnet/csharp/whats-new)
* [C# 언어 참조](/dotnet/csharp/language-reference/index)
* [초보자를 위한 C# 기본 사항](https://mva.microsoft.com/en-US/training-courses/c-fundamentals-for-absolute-beginners-16169) 비디오 과정
