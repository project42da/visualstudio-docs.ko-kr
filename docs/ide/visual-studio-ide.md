---
title: "Visual Studio IDE | Microsoft Docs"
ms.custom: ""
ms.date: "01/17/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 772b6cf4-cee5-42d0-bc18-b4eb07e22ff0
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# <a name="visual-studio-ide"></a>Visual Studio IDE
Microsoft Visual Studio 2017 RC는 계획 단계에서 UI 디자인, 코딩, 테스트, 디버그, 코드 품질 및 성능 분석, 고객에게 배포 및 사용량에 대한 원격 분석 수집에 이르기까지 소프트웨어를 만들기 위한 도구 제품군입니다. 이러한 도구는 가능한 한 매끄럽게 작동하도록 설계되었으며, 모두 Visual Studio IDE(통합 개발 환경)를 통해 노출됩니다.  

 Visual Studio를 사용하여 모바일 클라이언트용 단순한 스토어 앱과 게임에서 엔터프라이즈 및 데이터 센터를 지원하는 대규모의 복잡한 시스템에 이르기까지 많은 종류의 응용 프로그램을 만들 수 있습니다. 다음과 같은 것을 만들 수 있습니다.  

 - Windows뿐 아니라 Android 및 iOS에서도 실행되는 앱과 게임.

 - ASP.NET, JQuery, AngularJS 및 기타 인기 있는 프레임워크를 기반으로 한 웹 사이트와 웹 서비스

 - 예를 들어 Azure, Office, Sharepoint, Hololens, Kinect, 사물 인터넷 등의 다양한 플랫폼 및 장치용 응용 프로그램

 - DirectX를 사용하는 다양한 Windows 장치(Xbox 포함)용 게임 및 그래픽 위주 응용 프로그램.


 Visual Studio는 기본적으로 C#, C 및 C++, JavaScript, TypeScript, F# 및 Visual Basic을 지원합니다. Visual Studio는 [Xamarin for Visual Studio](https://www.xamarin.com/visual-studio)를 통해 Xamarin과, [Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md) 확장을 통해 Unity와 같은 타사 응용 프로그램과, [Visual Studio Tools for Apache Cordova](../misc/get-started-with-visual-studio-tools-for-apache-cordova2.md)를 통해 Apache Cordova와 잘 작동하고 통합됩니다. [Visual Studio SDK](../extensibility/visual-studio-sdk.md)를 통해 특수 작업을 수행하는 사용자 지정 도구를 만들어 Visual Studio를 직접 확장할 수 있습니다.

## <a name="find-out-whats-new"></a>새로운 기능 확인
 이전에 Visual Studio를 사용해 보지 않았다면 [Visual Studio를 사용한 개발 시작](../ide/get-started-with-visual-studio.md)에서 기본 사항에 대해 알아보세요.
Visual Studio 2017 RC의 새로운 기능에 대한 자세한 내용은 [Visual Studio 2017 RC의 새로운 기능](../ide/whats-new-in-visual-studio.md)을 참조하세요.

## <a name="set-up-visual-studio"></a>Visual Studio 설정
 [Visual Studio 제품](https://www.visualstudio.com/products/)에서 적합한 Visual Studio 버전을 확인할 수 있습니다.

 [Visual Studio 다운로드](https://www.visualstudio.com/vs/)에서 Visual Studio 2017 RC를 다운로드하여 설치할 수 있습니다. 설치 프로세스에 대한 자세한 내용은 [Visual Studio 2017 RC 설치](https://go.microsoft.com/fwlink/?linkid=833223)를 참조하세요.

## <a name="quick-tour-of-the-ide"></a>IDE 둘러보기
 다음 이미지는 몇 가지 주요 도구 창과 함께 열린 프로젝트가 있는 Visual Studio IDE를 보여 줍니다.
 - [솔루션 탐색기](../ide/solutions-and-projects-in-visual-studio.md)를 사용하면 코드 파일을 보고 탐색할 수 있습니다.
 - [팀 탐색기](https://www.visualstudio.com/en-us/docs/connect/work-team-explorer)를 사용하면 [Git](https://git-scm.com/), [TFVC(Team Foundation 버전 제어)](https://www.visualstudio.com/en-us/docs/tfvc/overview) 등의 버전 제어 기술을 통해 작업 항목을 추적하고 다른 사용자와 코드를 공유할 수 있습니다.
 - [클라우드 탐색기](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resources-managing-with-cloud-explorer/)를 사용하면 가상 컴퓨터, 테이블, SQL 데이터베이스 등의 Azure 리소스를 보고 관리할 수 있습니다.
 - [편집기](../ide/writing-code-in-the-code-and-text-editor.md) 창을 사용하면 소스 코드 및 디자이너 데이터를 보고 편집할 수 있습니다.
 - [출력](../ide/reference/output-window.md) 창에는 컴파일, 실행, 디버그 등의 출력이 표시됩니다.


 ![Visual Studio IDE](../ide/media/visualstudioide.png "VisualStudioIDE")  

 ### <a name="sign-in"></a>로그인
  Visual Studio를 처음 시작할 때 Microsoft 계정이나 회사 또는 학교 계정으로 로그인할 수 있습니다. 로그인을 하면 창 레이아웃 등 여러 장치 간에 설정을 동기화하고 Azure 구독 및 Visual Studio Team Services와 같이 필요할 수 있는 서비스에 자동으로 연결할 수 있습니다. 구독 기반 라이선스가 있는 경우 라이선스 토큰을 최신 상태로 유지하기 위해 정기적으로 Visual Studio에 로그인해야 합니다. 제품 키 라이선스가 있는 경우 로그인할 필요가 없지만 로그인하면 더 편리하게 Azure, Office 365, Salesforce.com에서 Visual Studio Team Services 및 사용자 계정에 연결할 수 있습니다. 자세한 내용은 [Visual Studio에 로그인](../ide/signing-in-to-visual-studio.md)을 참조하세요.

  여러 개의 Visual Studio Team Services 계정, Azure 계정 또는 MSDN 구독이 있는 경우 연결하여 한 번의 로그인으로 모든 계정의 리소스와 서비스에 액세스할 수 있습니다. 자세한 내용은 [여러 사용자 계정으로 작업](../ide/work-with-multiple-user-accounts.md)을 참조하세요.

 ### <a name="stay-up-to-date"></a>최신 상태 유지
  제목 표시줄의 위쪽 모서리에 있는 플래그 알림 아이콘은 Visual Studio 또는 설치된 관련 구성 요소에 대한 업데이트가 있을 경우 알려줍니다. 이러한 알림을 해제할지 또는 관련 작업을 수행할지를 선택할 수 있습니다. 자세한 내용은 [Visual Studio 알림](../ide/visual-studio-notifications.md)을 참조하세요.

 ### <a name="find-things-and-get-help"></a>항목 찾기 및 도움말 보기
  바로 가기 키 또는 메뉴 위치를 모르는 경우 다음 스크린샷에서 빨간색 윤곽선이 있는 [빠른 실행](../ide/reference/quick-launch-environment-options-dialog-box.md) 창을 사용하여 Visual Studio 명령, 도구, 기능 등을 빠르게 찾을 수 있습니다. 찾으려는 내용을 입력하기만 하면 빠른 실행에서 관련 링크가 제공됩니다.

 !['새 프로젝트'의 빠른 실행 결과](../ide/media/Productivity_QuickLaunch.png "Productivity_QuickLaunch")

 Visual Studio에서 **F1** 키를 눌러 활성 창에 대한 온라인 도움말로 이동할 수 있습니다. 코드 편집기에서 **F1** 키를 눌러 API 또는 현재 캐럿 위치의 키워드에 대한 도움말 페이지로 이동할 수도 있습니다. 예를 들어 C# 파일에서 `System.String` 선언의 임의 위치나 끝에 캐럿을 배치하고 **F1** 키를 눌러 [String](assetId:///T:System.String?qualifyHint=False&autoUpgrade=True)에 대한 도움말 페이지로 이동합니다.

### <a name="give-feedback"></a>사용자 의견 제공
 원할 경우 언제든지 Visual Studio에 대한 피드백을 쉽게 보낼 수 있습니다. **빠른 실행** 옆의 제목 표시줄에 있는 피드백 아이콘을 클릭한 다음 **문제 보고** 또는 **제안하기**를 클릭합니다.

![사용자 의견 제공](../ide/media/VSIDE_reportproblem.png)

 Visual Studio의 시험판 버전에는 **이 제품 평가** 옵션도 있습니다. Microsoft는 이러한 의견을 모두 확인하고 제품을 개선하는 데 사용합니다. 자세한 내용은 [의견 보내기](../ide/talk-to-us.md)를 참조하세요.

### <a name="personalize-the-ide"></a>IDE 개인 설정
 개발 스타일에 맞게 창 레이아웃을 사용자 지정할 수 있습니다. 언제든지 창을 도킹하거나 부동 창으로 만들거나 숨길 수 있으며 전체 화면 모드로 편집기를 실행할 수도 있습니다. 특정 컨텍스트에 필요한 창만 표시하는 사용자 지정 창 레이아웃을 여러 개 만들고 저장할 수 있습니다. 예를 들어 코드 편집기만 표시되도록 전체 화면 레이아웃을 만들 수 있습니다. 또한 디버깅 및 팀 작업을 위해 다양한 레이아웃을 만들 수 있습니다. 자세한 내용은 [창 레이아웃 사용자 지정](../ide/customizing-window-layouts-in-visual-studio.md)을 참조하세요.

 다른 여러 방법으로 Visual Studio를 사용자 지정할 수 있으며, 여러 컴퓨터에서 작업하는 경우 설정을 로밍할 수 있습니다. 자세한 내용은 [IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

 거의 모든 항목에 대한 바로 가기 키가 있으며 사용자 지정할 수도 있습니다. 새 바로 가기를 만들려면 빠른 실행에서 "키보드"를 입력하여 키보드 대화 상자를 엽니다. 여기서 옵션에 대한 자세한 정보가 필요한 경우 F1 키를 눌러 도움말 페이지로 이동할 수 있습니다. 자세한 내용은 [Visual Studio의 기본 바로 가기 키](../ide/default-keyboard-shortcuts-in-visual-studio.md)를 참조하세요.

## <a name="connect-to-visual-studio-team-services-and-team-foundation-server"></a>Visual Studio Team Services 및 Team Foundation Server에 연결
  VSTS(Visual Studio Team Services)는 소프트웨어 프로젝트를 호스트하고 팀 공동 작업을 사용할 수 있도록 하는 클라우드 기반 서비스입니다. VSTS는 Git 및 Team Foundation 소스 제어 시스템과 Scrum, CMMI 및 Agile 개발 방법론을 지원합니다. TFVC(Team Foundation 버전 제어)는 하나의 중앙 집중식 서버 리포지토리를 사용하여 파일을 추적하고 버전을 관리합니다. 다른 개발자가 최신 변경 내용을 가져올 수 있는 중앙 서버에 로컬 변경 내용이 항상 체크 인됩니다. Team Foundation Server(TFS) 2015는 Visual Studio용 응용 프로그램 수명 주기 관리 허브입니다. 개발 프로세스와 관련된 모든 사람이 단일 솔루션을 사용하여 참여할 수 있도록 해줍니다. TFS는 성격이 다른 팀과 프로젝트들을 관리하는 데 유용합니다.

  네트워크에 Visual Studio Team Services 계정 또는 Team Foundation Server가 있는 경우 팀 탐색기 창을 통해 연결합니다. 이 창에서 코드를 소스 제어에 체크 인 또는 체크 아웃하고, 작업 항목을 관리하고, 빌드를 시작하고, 단체 방 및 작업 영역에 액세스할 수 있습니다. **빠른 실행**이나 **보기 | 팀 탐색기** 또는 **팀 | 연결 관리**의 주 메뉴에서 팀 탐색기를 열 수 있습니다.  Visual Studio Team Services에 대한 자세한 내용은 [www.visualstudio.com](https://www.visualstudio.com/)을 참조하세요. Team Foundation Server에 대한 자세한 내용은 [Team Foundation Server](https://www.visualstudio.com/products/tfs-overview-vs)를 참조하세요.

  다음 이미지는 VSTS에서 호스트되는 솔루션용 팀 탐색기 창을 보여 줍니다.

 ![Visual Studio 팀 탐색기](../ide/media/vs2017_teamexplorer.png "VS2017_TeamExplorer")  

## <a name="create-solutions-and-projects"></a>솔루션 및 프로젝트 만들기
  Visual Studio를 사용하여 개별 코드 파일을 찾을 수 있지만 *프로젝트*로 작업하는 것이 더 일반적입니다. Visual Studio 프로젝트는 응용 프로그램의 경우 단일 이진 실행 파일(예: .exe, DLL 또는 appx)로 컴파일되는 파일 및 리소스의 컬렉션입니다. 비 ASP.NET 웹 사이트의 경우 실행 파일이 생성되지 않으며 프로젝트에는 HTML, JavaScript 파일 및 이미지만 포함됩니다. 경우에 따라 긴밀히 관련된 여러 이진 파일이나 웹 사이트를 만들어야 할 수 있으므로 Visual Studio에는 여러 프로젝트나 웹 사이트를 포함할 수 있는 솔루션 개념이 있습니다. 프로젝트를 만드는 경우 실제로는 한 솔루션에 하나의 프로젝트를 만드는 것이며 필요에 따라 나중에 더 많은 프로젝트를 솔루션에 추가할 수 있습니다. 예를 들어 DLL 프로젝트가 있는 경우 DLL을 로드 및 사용하는 솔루션에 .exe 프로젝트를 추가할 수 있습니다.

  *프로젝트 템플릿* 은 특정 종류의 응용 프로그램을 신속하게 설정할 수 있게 해주는 미리 채워진 코드 파일 및 구성 설정의 컬렉션입니다. Visual Studio에는 선택할 수 있는 많은 프로젝트 템플릿이 있으며, 적합한 기본 템플릿이 없는 경우 고유한 템플릿을 만들 수 있습니다. 템플릿을 사용하여 프로젝트를 만든 후 제공된 파일이나 직접 추가한 새 파일에서 고유한 코드를 작성할 수 있습니다. 자세한 내용은 [솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)를 참조하세요. 다음 그림에서는 ASP.NET 응용 프로그램에서 사용할 수 있는 프로젝트 템플릿이 포함된 새 프로젝트 대화 상자를 보여 줍니다.

 ![Visual Studio 새 프로젝트 대화 상자](../ide/media/vs2017_newprojectdialog.png "VS2017_NewProjectDialog")  

## <a name="write-navigate-and-understand-code"></a>코드 작성, 탐색 및 이해  
 개발자인 경우 편집기 창에서 대부분의 시간을 보낼 것입니다. Visual Studio에는 C#, C++, Visual Basic, F#, JavaScript, TypeScript, XML, HTML 및 CSS에 대한 기본 제공 편집 지원이 포함되어 있습니다. Visual Studio는 다른 많은 언어에 대해서도 편집 및 컴파일을 지원합니다.

 **파일, 열기, 파일**을 선택하여 텍스트 편집기에서 개별 파일을 편집할 수 있습니다. 열린 프로젝트에서 파일을 편집하려면 솔루션 탐색기에서 파일 이름을 선택하고 엽니다. 코드에는 색이 지정되며 빠른 실행에서 "색"을 입력하여 색 구성표를 개인 설정할 수 있습니다. 한 번에 많은 텍스트 편집기 탭 창을 열어 둘 수 있습니다. 각 창을 독립적으로 분할할 수 있습니다. 텍스트 편집기를 전체 화면 모드로 실행할 수도 있습니다.  

 ![코드 편집기의 코드](../ide/media/codewindow.png "코드 편집기")  

 텍스트 편집기는 보다 효율적인 코드를 더 빠르게 작성할 수 있도록 도와주는 많은 생산성 기능이 포함된 대화형(원할 경우)입니다. 기능은 언어에 따라 달라지며, 기능을 설정하거나 해제하기 위해 언어를 사용할 필요가 없습니다(빠른 실행에서 "편집기" 입력). 몇 가지 일반적인 생산성 기능은 다음과 같습니다.  

-  [리팩터링](../ide/refactoring-in-visual-studio.md)에는 변수의 지능형 이름 바꾸기, 선택한 코드 줄을 별도 함수로 이동, 코드를 다른 위치로 이동, 함수 매개 변수 다시 정렬 등의 작업이 포함되어 있습니다.

  ![리팩터링](../ide/media/VSIDE_refactor.png)  

-  **IntelliSense**는 편집기에서 직접 코드에 대한 형식 정보를 표시하고 경우에 따라 약간의 코드를 자동으로 작성하는 인기 있는 기능 집합에 대한 포괄적인 용어입니다. IntelliSense는 별도의 도움말 창에서 형식 정보를 조회할 필요가 없도록 기본 설명서를 편집기에 인라인으로 포함하는 것과 같습니다. IntelliSense 기능은 언어에 따라 달라집니다. 자세한 내용은 [Visual C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ Intellisense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), [Visual Basic-Specific IntelliSense](../ide/visual-basic-specific-intellisense.md)를 참조하세요. 다음 그림에서는 일부 IntelliSense 기능의 작동을 보여 줍니다.  

     ![Visual Studio 멤버 목록](../ide/media/vs2017_Intellisense.png "vs2017_Intellisense")  

-  **오류 표시선** 은 입력하는 동안 코드의 오류 또는 잠재적 문제를 실시간으로 경고하여 컴파일 또는 런타임 중에 오류가 검색될 때까지 기다리지 않고 즉시 수정할 수 있게 해줍니다. 오류 표시선 위로 마우스를 가져가면 오류에 대한 추가 정보가 표시됩니다. 오류를 수정하는 방법에 대한 제안 사항과 함께 전구가 왼쪽 여백에 나타날 수도 있습니다. 자세한 내용은 [전구를 사용하여 빠른 작업 수행](../ide/perform-quick-actions-with-light-bulbs.md)을 참조하세요.  

  ![물결선](../ide/media/vs2017_squiggle.png "VS2017_Squiggles")  

-  [책갈피](../ide/setting-bookmarks-in-code.md)를 사용하면 작업 중인 파일의 특정 줄로 빠르게 이동할 수 있습니다.

    ![책갈피 창](../ide/media/VSIDE_bookmarks.png)

-  텍스트 편집기 상황에 맞는 메뉴에서 [호출 계층 구조](../ide/reference/call-hierarchy.md) 창을 호출하여 캐럿 아래의 메서드를 호출하고 해당 메서드에 의해 호출되는 메서드를 표시할 수 있습니다.

    ![호출 계층 구조 창](../ide/media/VSIDE_call_hierarchy.png)

-  **코드 렌즈**를 사용하면 편집기 내에서 코드 참조, 코드 변경 내용, 연결된 버그, 작업 항목, 코드 검토 및 단위 테스트를 확인할 수 있습니다.

    ![CodeLens](../ide/media/codelensoverview.png)

  자세한 내용은 [코드 변경 내용 및 기타 기록 찾기](../ide/find-code-changes-and-other-history-with-codelens.md)를 참조하세요.  

-  **정의 보기** 창은 현재 컨텍스트를 벗어나지 않고 메서드 또는 형식 정의를 인라인으로 표시합니다. 이제 이 창이 XAML에서도 작동합니다.  

    ![정의 피킹(Peeking)](../ide/media/VSIDE_peek_definition.png)

-  **정의로 이동** 상황에 맞는 메뉴 옵션은 함수 또는 개체가 정의된 위치로 바로 이동합니다. 편집기에서 마우스 오른쪽 단추를 클릭하면 다른 탐색 명령도 사용할 수 있습니다.

    ![정의로 이동](../ide/media/VSIDE_go_to_definition.png)

- 관련 도구인 [개체 브라우저](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)를 통해 시스템에서 .NET 또는 Windows 런타임 어셈블리를 검사하여 포함된 형식과 해당 형식이 포함하는 메서드 및 속성을 확인할 수 있습니다.  

     ![System.Timer를 보여 주는 개체 브라우저](../ide/media/objectbrowser.png "ObjectBrowser")  

 편집 메뉴 및 보기 메뉴의 항목은 대부분 어떤 방식으로든 코드 편집기와 관련이 있습니다. 편집기에 대한 자세한 내용은 [코드 작성](../ide/writing-code-in-the-code-and-text-editor.md) 및 [코드 편집](https://www.visualstudio.com/features/ide-vs)을 참조하세요.  

## <a name="compile-and-build-your-code"></a>코드 컴파일 및 빌드  
 프로젝트를 빌드하려면 소스 코드를 컴파일하고 실행 파일을 생성하는 데 필요한 단계를 수행해야 합니다. 언어마다 다른 빌드 작업이 있으며 일반적인 웹 사이트는 빌드되지 않습니다. 프로젝트 형식에 관계없이 **빌드** 메뉴가 이러한 명령의 표준 위치입니다. 단일 키 입력으로 코드를 컴파일하고 실행하려면 F5 키를 누릅니다. 모든 컴파일러는 IDE를 통해 완전히 구성할 수 있습니다. 빌드 도구 모음을 사용하면 디버거에서 중단점 및 한 단계씩 실행을 지원하기 위해 기호 및 추가 오류 검사를 사용할 수 있는 프로그램의 디버그 버전을 빌드할지, 아니면 궁극적으로 사용자에게 제공할 릴리스 버전을 빌드할지를 지정할 수 있습니다. 프로젝트 속성 페이지에서 자세한 빌드 설정과 기타 많은 설정을 구성할 수 있습니다. 솔루션 탐색기에서 프로젝트 노드의 상황에 맞는(마우스 오른쪽 단추 클릭) 메뉴를 선택한 다음 속성 명령을 선택합니다. 명령줄에서 빌드를 실행할 수도 있습니다.  

 오류 또는 성공 메시지를 포함하는 빌드 출력이 출력 창에 나타납니다. 오류 목록(아래 참조)에서는 빌드 오류에 대한 자세한 정보를 제공합니다.  

 ![C&#35; 컴파일러 오류를 표시하는 오류 목록](../ide/media/VS2017_errorlist.png "VS2017_error_list")  

## <a name="debug-your-code"></a>코드 디버그  
 Visual Studio의 최신 디버거를 사용하면 로컬 프로젝트나 원격 장치 또는 Android 또는 Windows Phone 장치용 에뮬레이터와 같은 에뮬레이터에서 실행 중인 코드를 디버그할 수 있습니다. 한 번에 문 하나씩 코드를 단계별로 실행하고 진행에 따라 변수를 검사하고, 다중 스레드 응용 프로그램을 단계별로 실행하고, 지정된 조건이 true일 때만 적중되는 중단점을 설정할 수 있습니다. 코드가 실행될 때 변수 값을 모니터링할 수 있습니다. 코드의 컨텍스트에서 나갈 필요가 없도록 이러한 모든 작업을 코드 편집기 자체에서 관리할 수 있습니다.  

 ![중단점 설정 미리 보기 창](../ide/media/dbg_breakpoints_peekwindow.png "DBG_Breakpoints_PeekWindow")  

 디버거 자체에 포함된 여러 개의 창을 통해 지역 변수, 호출 스택 및 런타임 환경의 기타 측면을 보고 조작할 수 있습니다. 이러한 창은 **디버그** 메뉴에서 찾을 수 있습니다.  

 [직접 실행 창](../ide/reference/immediate-window.md)에서는 식을 입력하고 결과를 즉시 확인할 수 있습니다.

![직접 실행 창](../ide/media/VSIDE_immediate_window.png)

 [IntelliTrace](../debugger/intellitrace.md) 창은 실행 중인 .NET 프로그램의 각 메서드 호출 및 기타 이벤트를 기록하며, 문제가 발생한 위치를 빠르게 찾을 수 있도록 도와줍니다.

 자세한 내용은 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)을 참조하세요.  

## <a name="test-your-code"></a>코드 테스트  
 Visual Studio에는 관리 코드(.NET)에 대한 단위 테스트 프레임워크와 네이티브 C++에 대한 단위 테스트 프레임워크가 포함되어 있습니다. 단위 테스트를 만들려면 솔루션에 테스트 프로젝트를 추가하고 테스트를 작성한 다음 테스트 탐색기 창에서 실행하면 됩니다. 자세한 내용은 [코드 단위 테스트](../test/unit-test-your-code.md)를 참조하세요.  

 ![단위 테스트 탐색기](../ide/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  

## <a name="analyze-code-quality-and-performance"></a>코드 품질 및 성능 분석  
 Visual Studio에는 정적 및 런타임 분석을 위한 강력한 도구가 포함되어 있습니다. 정적 분석 도구는 디자인, 세계화, 상호 운용성, 성능, 보안 및 기타 범주의 잠재적 오류를 식별하는 데 도움이 됩니다. 성능 테스트 또는 프로파일링에는 프로그램이 실행되는 방식을 측정하는 작업이 포함됩니다. 이러한 도구는 **분석** 메뉴에서 액세스합니다. 자세한 내용은 [Visual Studio 진단 도구로 품질 개선](../test/improve-code-quality.md)을 참조하세요.  

## <a name="connect-to-cloud-services-and-databases"></a>클라우드 서비스 및 데이터베이스에 연결  
 Visual Studio의 [클라우드 탐색기](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resources-managing-with-cloud-explorer/)에서는 로그인한 Azure 구독으로 관리되는 모든 계정의 Azure 리소스를 보여 줍니다. [Azure SDK](https://azure.microsoft.com/en-us/downloads/)를 설치하여 클라우드 탐색기를 얻을 수 있습니다.


 ![클라우드 탐색기](../ide/media/VSIDE_CloudExplorer.png)

 [서버 탐색기](https://msdn.microsoft.com/en-us/library/cd2cz7yy.aspx)를 사용하여 Azure, Salesforce.com, Office 365 및 웹 사이트에서 SQL Server 인스턴스와 자산을 찾고 관리할 수 있습니다.

 Visual Studio에는 데이터베이스를 빌드, 디버그, 유지 관리 및 리팩터링할 수 있게 해주는 [Microsoft SSDT(SQL Server Data Tools)](https://msdn.microsoft.com/en-us/data/tools.aspx) 가 포함되어 있습니다. 데이터베이스 프로젝트에 대해 작업하거나, 온-프레미스 또는 오프-프레미스로 연결된 데이터베이스 인스턴스에 대해 직접 작업할 수 있습니다.  

 Visual Studio의 [SQL Server 개체 탐색기](https://msdn.microsoft.com/en-us/library/hh231250.aspx)는 SQL Server Management Studio와 비슷한 방식으로 데이터베이스 개체 뷰를 제공합니다. SQL Server 개체 탐색기에서는 테이블 데이터 편집, 스키마 비교 및 SQL Server 개체 탐색기에서 바로 상황에 맞는 메뉴를 통해 쿼리 실행을 포함하여 간단한 데이터베이스 관리 및 디자인 작업을 수행할 수 있습니다. SSDT에는 SQL Server 2012 Analysis Services, Reporting Services 및 Integration Services BI(Business Intelligence) 솔루션(이전의 Business Intelligence Development Studio)을 개발하기 위한 특수 프로젝트 형식 및 도구도 포함되어 있습니다.  

 ![SQL Server 개체 탐색기](../ide/media/vs2015_sqlobjectexplorer.png "vs2015_SQLObjectExplorer")  

## <a name="deploy-your-finished-application"></a>완성된 응용 프로그램 배포  
 응용 프로그램을 고객에게 배포할 준비가 되면 Visual Studio에서는 Windows 스토어 또는 Sharepoint 사이트에 배포하는지, 아니면 Installshield 또는 Windows Installer 기술을 통해 배포하는지에 관계없이 배포 작업을 수행하는 도구를 제공합니다. 모든 도구는 IDE를 통해 액세스할 수 있습니다. 자세한 내용은 [응용 프로그램, 서비스 및 구성 요소 배포](../deployment/deploying-applications-services-and-components.md)를 참조하세요.  

## <a name="architecture-and-modeling-tools-enterprise-only"></a>아키텍처 및 모델링 도구(Enterprise만 해당)  
 Visual Studio 아키텍처 및 모델링 도구를 사용하여 앱을 디자인하고 모델링할 수 있습니다. 이러한 도구는 코드의 구조, 동작 및 관계를 시각화하는 데 도움이 됩니다. 개발 프로세스의 일부로 응용 프로그램 수명 주기 전체에 걸쳐 다양한 상세 수준으로 모델을 만들 수 있습니다. 모델 요소를 Team Foundation Server 작업 항목 및 개발 계획에 연결하여 요구 사항, 작업, 테스트 사례, 버그 및 모델과 연결된 기타 작업을 추적할 수 있습니다. 자세한 내용은 [앱 디자인 및 모델링](../modeling/analyze-and-model-your-architecture.md)을 참조하세요.  

## <a name="extend-visual-studio-through-the-visual-studio-sdk"></a>Visual Studio SDK를 통해 Visual Studio 확장  
 Visual Studio는 확장 가능한 플랫폼입니다. Visual Studio 확장은 IDE와 통합되는 사용자 지정 도구입니다. 타사 확장을 추가하거나 고유한 확장을 만들 수 있습니다. 자세한 내용은 [Visual Studio 확장 개발 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)을 참조하세요.  

 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)은 Visual Studio용 확장을 작성하는 모든 사용자가 반드시 참조해야 하는 내용입니다. 이 플랫폼별 지침에는 대화 상자 디자인, 글꼴, 색, 아이콘, 공용 컨트롤뿐만 아니라, 새로운 기능이 Visual Studio와 완벽하게 통합되도록 만들어 줄 기타 정보까지 포함되어 있습니다.  

## <a name="see-also"></a>참고 항목  
 [Visual Studio 2017 RC 설치](../install/install-visual-studio.md)   
 [코드 편집](https://www.visualstudio.com/features/ide-vs)   
 [Visual Studio 2017 RC의 새로운 기능](../ide/whats-new-in-visual-studio.md)   
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [의견 보내기](../ide/talk-to-us.md)



<!--HONumber=Feb17_HO4-->


