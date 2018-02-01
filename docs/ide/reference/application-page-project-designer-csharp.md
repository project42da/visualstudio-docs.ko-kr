---
title: "프로젝트 디자이너, 응용 프로그램 페이지(C#) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesApplicationWPF
- cs.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 7f9b348ad39b26b22e1678e76a1310e2c3f9b863
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="application-page-project-designer-c"></a>프로젝트 디자이너, 응용 프로그램 페이지(C#)

**프로젝트 디자이너**의 **응용 프로그램** 페이지를 사용하여 프로젝트의 응용 프로그램 설정과 속성을 지정할 수 있습니다.  
  
**응용 프로그램** 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드(**솔루션** 노드 아님)를 선택합니다. 그런 다음 메뉴 모음에서 **프로젝트**, **속성**을 선택합니다. 프로젝트 디자이너가 나타나면 **응용 프로그램** 탭을 클릭합니다.  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="general-application-settings"></a>일반 응용 프로그램 설정  
 다음 옵션을 사용하여 응용 프로그램에 대한 일반 설정을 구성할 수 있습니다.  
  
 **어셈블리 이름**  
 어셈블리 매니페스트를 보유할 출력 파일의 이름을 지정합니다. 이 속성을 변경하면 **출력 이름** 속성도 변경됩니다. [/out(C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option)을 사용하여 명령줄에서 이 변경을 수행할 수도 있습니다. 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:VSLangProj.ProjectProperties.AssemblyName%2A>을 참조하세요.  
  
 **기본 네임스페이스**  
 프로젝트에 추가된 파일에 대한 기본 네임스페이스를 지정합니다.  
  
 코드에서 네임스페이스를 만드는 방법에 대한 자세한 내용은 [네임스페이스](/dotnet/csharp/language-reference/keywords/namespace)를 참조하세요.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:VSLangProj.ProjectProperties.RootNamespace%2A>을 참조하세요.  
  
 **대상 프레임워크**  
 응용 프로그램의 대상 .NET Framework 버전을 지정합니다. 이 옵션은 컴퓨터에 설치된 .NET Framework 버전에 따라 다른 값을 가질 수 있습니다.  
  
 기본값은 **새 프로젝트** 대화 상자에서 선택한 대상 프레임워크와 같습니다.  
  
> [!NOTE]
>  대화 상자를 처음 열면 [필수 조건 대화 상자](../../ide/reference/prerequisites-dialog-box.md)에 나열된 필수 조건 패키지가 자동으로 설정됩니다. 이후에 프로젝트의 대상 프레임워크를 변경하는 경우에는 새 대상 프레임워크에 맞도록 필수 구성 요소를 수동으로 선택해야 합니다.  
  
 자세한 내용은 [방법: 대상 .NET Framework 버전 지정](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) 및 [Visual Studio 멀티 타기팅 개요](../../ide/visual-studio-multi-targeting-overview.md)를 참조하세요.  
  
 **응용 프로그램 종류**  
 빌드할 응용 프로그램 종류를 지정합니다. Windows 8.x 앱의 경우 **Windows Store 앱**, **클래스 라이브러리** 또는 **WinMD 파일**을 지정할 수 있습니다. 다른 응용 프로그램 종류의 경우 대부분 **Windows 응용 프로그램**, **콘솔 응용 프로그램**, **클래스 라이브러리**, **Windows 서비스** 또는 **웹 컨트롤 라이브러리**를 지정할 수 있습니다.  
  
 웹 응용 프로그램 프로젝트의 경우 **클래스 라이브러리**를 지정해야 합니다.  
  
 **WinMD 파일** 옵션을 지정하는 경우 유형을 Windows 런타임 프로그래밍 언어로 프로젝션할 수 있습니다. 프로젝트의 출력을 WinMD 파일로 패키징하면 여러 언어로 응용 프로그램을 코딩한 후 모두 동일한 언어로 작성한 것처럼 코드가 상호 운용되도록 할 수 있습니다. [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] 앱을 포함하여 Windows 런타임 라이브러리를 대상으로 하는 솔루션에 대해 이 옵션을 사용할 수 있습니다. 자세한 내용은[C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)를 참조하세요.  
  
> [!NOTE]
>  Windows 런타임은 어떤 언어에서 사용하든 네이티브 개체로 나타나도록 유형을 프로젝션할 수 있습니다. 예를 들어 Windows 런타임과 상호 작용하는 JavaScript 응용 프로그램에서는 JavaScript 개체 집합으로 사용되고, C# 응용 프로그램에서는 라이브러리가 .NET 개체 컬렉션으로 사용됩니다. 프로젝트의 출력을 WinMD 파일로 패키징하면 Windows 런타임에서 사용되는 것과 동일한 기술을 이용할 수 있습니다.  
  
 **응용 프로그램 종류** 속성에 대한 자세한 내용은 [/target(C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option)을 참조하세요. 프로그래밍 방식으로 이 속성에 액세스하는 방법에 대한 자세한 내용은 <xref:VSLangProj.ProjectProperties.OutputType%2A>을 참조하세요.  
  
 **어셈블리 정보**  
 이 단추를 클릭하면 [어셈블리 정보 대화 상자](../../ide/reference/assembly-information-dialog-box.md)가 표시됩니다.  
  
 **시작 개체**  
 응용 프로그램 로드 시 호출할 진입점을 정의합니다. 일반적으로 응용 프로그램의 기본 폼이나 응용 프로그램 시작 시 실행되어야 하는 `Main` 프로시저로 설정됩니다. 클래스 라이브러리에 진입점이 없기 때문에 이 속성의 유일한 옵션은 **(설정 안 함)**입니다.  
  
 기본적으로, WPF 브라우저 응용 프로그램 프로젝트에서 이 옵션은 **(설정 안 함)**입니다. 다른 옵션은 *Projectname*.App입니다. 이러한 종류의 프로젝트에서는 응용 프로그램을 시작할 때 UI 리소스를 로드하도록 시작 URI를 설정해야 합니다. 이렇게 하려면 프로젝트에서 Application.xaml 파일을 열고 `StartupUri` 속성을 프로젝트의 .xaml 파일(예: Window1.xaml)로 설정합니다. 허용되는 루트 요소 목록은 <xref:System.Windows.Application.StartupUri%2A>를 참조하세요. 또한 프로젝트의 클래스에서 `public static void Main()` 메서드를 정의해야 합니다. 이 클래스는 **시작 개체** 목록에 *ProjectName.ClassName*으로 나타납니다. 그런 다음 클래스를 시작 개체로 선택할 수 있습니다.  
  
 자세한 내용은 [/main(C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option)을 참조하세요. 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:VSLangProj.ProjectProperties.StartupObject%2A>을 참조하세요.  
  
## <a name="resources"></a>리소스  
 다음 옵션을 사용하여 응용 프로그램에 대한 일반 설정을 구성할 수 있습니다.  
  
 **아이콘 및 매니페스트**  
 기본적으로 이 라디오 단추는 선택되며 **아이콘** 및 **매니페스트** 옵션이 사용됩니다. 이렇게 하면 사용자 고유의 아이콘을 선택하거나 다른 매니페스트 생성 옵션을 선택할 수 있습니다. 프로젝트에 대한 리소스 파일을 제공하지 않는 경우 이 라디오 단추를 선택된 상태로 둡니다.  
  
 **아이콘**  
 프로그램 아이콘으로 사용할 .ico 파일을 설정합니다. 줄임표(...) 단추를 클릭하여 기존 그래픽을 찾거나 원하는 파일의 이름을 입력합니다. 자세한 내용은 [/win32icon(C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option)을 참조하세요. 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>을 참조하세요.  
  
 **Manifest**  
 Windows Vista에서 UAC(사용자 계정 컨트롤)로 응용 프로그램을 실행하는 경우 매니페스트 생성 옵션을 선택합니다. 이 옵션은 다음 값을 가질 수 있습니다.  
  
-   **기본 설정으로 구성된 매니페스트 포함** Windows Vista에서 Visual Studio가 작동하는 일반적인 방식(`requestedExecutionLevel`을 `AsInvoker`로 지정하여 응용 프로그램의 실행 파일에 보안 정보 포함)을 지원합니다. 기본 옵션입니다.  
  
-   **매니페스트 없이 응용 프로그램 만들기** 이 방법을 *가상화*라고 합니다. 이 옵션은 이전 응용 프로그램과의 호환성을 위해 사용합니다.  
  
-   **Properties\app.manifest**. 이 옵션은 ClickOnce 또는 등록이 필요하지 않은 COM에 의해 배포된 응용 프로그램에 필요합니다. ClickOnce 배포를 사용하여 응용 프로그램을 게시하면 **매니페스트**가 자동으로 이 옵션으로 설정됩니다.  
  
**리소스 파일**  
프로젝트에 대한 리소스 파일을 제공하는 경우 이 라디오 단추를 선택합니다. 이 옵션을 선택하면 **아이콘** 및 **매니페스트** 옵션이 사용되지 않습니다.  
  
경로 이름을 입력하거나 찾아보기 단추(**...**)를 사용하여 Win32 리소스 파일을 프로젝트에 추가합니다.