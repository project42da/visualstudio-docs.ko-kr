---
title: Xamarin Studio 대비 Mac용 Visual Studio의 이점
description: ''
ms.topic: overview
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 6ACF5FD4-D5C1-4050-95E3-467C753F25F1
ms.openlocfilehash: db4a328bceb79c1b99fdea95da89cc6cc7451523
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="benefits-of-visual-studio-for-mac-over-xamarin-studio"></a>Xamarin Studio 대비 Mac용 Visual Studio의 이점 

Mac용 Visual Studio는 모든 기능을 갖춘 Mac의 IDE로 Xamarin Studio를 대체했습니다. 웹 응용 프로그램 및 서비스, 플랫폼 간 모바일 및 데스크톱 앱, 게임을 개발할 수 있는 기능을 제공합니다. 또한 Azure에 게시, Azure Functions 생성 등 Azure와 쉽게 통합되도록 합니다. Mac용 Visual Studio에는 모든 기능을 갖춘 소스 편집기, 효과적인 디버거, 사용자 지정 가능한 작업 영역, Git 통합, 풍부한 확장 시스템 등 최신 IDE에서 기대하는 모든 기능이 포함되어 있습니다. 기본적으로 모든 기능이 Mac용으로 디자인되었습니다. 

이러한 기능에는 다음이 포함됩니다. 

* Roslyn 기반 C# IntelliSense, 리팩터링, 분석기 및 코드 수정 
* NuGet 기반 패키지 관리 
* Visual Studio 호환 가능한 프로젝트 형식 
* MSBuild 빌드 엔진 
* 통합 유닛 테스트 
* F#에 대한 기본 제공 지원 

이 가이드에서 **미리 보기**로 표시된 이점은 [알파 채널](https://docs.microsoft.com/visualstudio/mac/update#Changing_the_Updater_channel)에서만 사용할 수 있습니다. 

## <a name="language-support"></a>언어 지원 

Mac에서 C# 7 코드를 작성하는 기능은 Mac용 Visual Studio에서만 제공됩니다.

## <a name="net-core"></a>.NET Core  

[.NET Core](https://www.microsoft.com/net/core#macos)는 Windows, Linux 및 Mac에서 실행되는 응용 프로그램을 만들기 위한 플랫폼입니다. Mac용 Visual Studio에서는 .NET Core 프로젝트의 로드, 생성, 실행 및 디버그를 지원합니다. 

.NET Core는 Mac용 Visual Studio와 함께 설치되며 바로 작동 가능합니다.

.NET Core 지원에는 다음이 포함됩니다. 

* C# 및 F# IntelliSense 
* 콘솔, 라이브러리 및 웹 응용 프로그램용 .NET Core 프로젝트 템플릿 
* 중단점, 호출 스택, 조사식 창 등을 포함하는 전체 디버깅 지원 
* NuGet 패키지 참조 및 MSBuild 기반 복원 
* .NET Core SDK에 포함된 Visual Studio 테스트 플랫폼을 사용하여 테스트를 실행 및 디버그하기 위한 통합 유닛 테스트 지원 
* 이전 project.json 형식에서의 마이그레이션 
* .NET Standard 프로젝트 지원

## <a name="web-development"></a>웹 개발  

### <a name="aspnet-core"></a>ASP.NET Core 

Mac용 Visual Studio에는 MVC 및 Web API 프로젝트용 ASP.NET Core 템플릿이 기본 제공됩니다.
 
![HTML IntelliSense](media/benefits-vsmac-over-xs-image3.png)

Mac용 Visual Studio에서는 HTML, CSS 및 JSON 파일에 대한 새로운 웹 도구 지원도 추가적으로 제공합니다. 

### <a name="html"></a>HTML 

* 새 HTML 템플릿 
* 향상된 스마트 들여쓰기 및 서식 지정 
* 향상된 색 지정 
* 향상된 IntelliSense 
* 코드 접기(사용하도록 설정해야 함) 
* 명령 축소 
* 향상된 코드 템플릿(조각) 
* `<div>`를 사용하여 선택한 코드 감싸기 
* 옵션 위로/아래로를 사용하면 선택한 텍스트가 위/아래로 이동됩니다. 

### <a name="css"></a>CSS 

* 향상된 스마트 들여쓰기 및 서식 지정 
* 향상된 색 지정 
* 향상된 IntelliSense 
* 코드 접기 
* 다양한 코드 템플릿(조각) 
* 옵션 위로/아래로를 사용하면 선택한 텍스트가 위/아래로 이동됩니다. 

### <a name="json"></a>JSON 
* schemastore.org에 액세스할 수 있는 스키마 선택 기능 
* 스키마의 유효성 검사 
* 스키마의 IntelliSense 
* 향상된 스마트 들여쓰기 및 서식 지정 
* 향상된 색 지정 
* 주석 처리/주석 처리 제거 
* 큰따옴표 삽입 및 중괄호 일치 
* 옵션 위로/아래로를 사용하면 선택한 텍스트가 위/아래로 이동됩니다. 

## <a name="publishing-to-azure"></a>Azure에 게시

Mac용 Visual Studio를 사용하면 ASP.NET Core 웹앱과 서비스를 Azure App Service에 게시할 수 있습니다. 

![Azure에 게시](media/benefits-vsmac-over-xs-image1.png)

### <a name="azure-functions-preview"></a>Azure Functions(**미리 보기**)

Azure Functions는 클라우드에서 소량의 코드 또는 함수를 쉽게 실행하기 위한 솔루션입니다. Mac용 Visual Studio를 사용하면 Azure Functions를 코딩하고 로컬에서 디버그할 수 있습니다. 시작하려면 새 프로젝트 대화 상자의 클라우드 아래에서 Azure Functions를 찾습니다. 

### <a name="docker-support-preview"></a>Docker 지원(**미리 보기**)

이제 Docker 컨테이너에 ASP.NET Core 앱을 게시하고 Azure App Service에서 실행할 수 있습니다. 

프로젝트에서 Docker 지원을 사용하도록 설정하려면 ASP.NET Core 웹앱을 마우스 오른쪽 단추로 클릭하고 **추가 > Docker 지원 추가**를 선택합니다. 

Docker 컨테이너에 웹앱을 게시하려면 Mac용 Visual Studio에서 도입된 **게시 > Azure에 게시** 워크플로를 사용합니다.

## <a name="source-editor-improvements"></a>소스 편집기 개선 사항 

Roslyn 기반 C# IntelliSense, 리팩터링, 분석기, 코드 수정 외에도 Mac용 Visual Studio 소스 편집기에서는 Xamarin Studio 대비 다음과 같은 향상된 기능을 제공합니다. 

### <a name="language-bundles"></a>언어 번들 

Mac용 Visual Studio는 다음을 추가하는 데 사용할 수 있는 TextMate(`.tmBundle`) 및 sublime 3(`.sublime`) 언어 번들을 지원합니다. 

* 편집기 색 테마 
* 코드 조각 
* 새 언어에 대한 문법, 강조 표시 및 기본 IntelliSense 사용 

**기본 설정 > 텍스트 편집기 > 언어 번들**에서 이러한 번들을 추가할 수 있습니다. 

### <a name="color-theme-support"></a>색 테마 지원 

Mac용 Visual Studio에서 지원되는 색 테마 형식은 다음과 같습니다. 

* Visual Studio(`.vssettings`) 
* Xamarin Studio(`.json`) 
* TextMate(`tmTheme`) 

## <a name="unity"></a>Unity 

[Unity](https://unity3d.com/)는 모바일, 데스크톱, 콘솔, AR, VR 장치, 웹 등 모든 주요 플랫폼에 대한 고품질 플랫폼 간 2D 및 3D 게임을 만드는 데 사용할 수 있는 게임 제작 도구입니다. 

Unity 5.6.1부터 Mac용 Visual Studio를 사용하여 Unity 게임을 작성 및 디버그할 수 있습니다. 시작하려면 Visual Studio를 Unity 5.6.1 스크립트 편집기로 설정합니다. 

Tools for Unity에는 다음과 같은 기능이 포함되어 있습니다. 

* C#으로 작성된 스크립트 지원 
* Unity Solution Pad 
* Unity 편집기의 원클릭 디버깅 
* Unity 메시지에 대한 IntelliSense 
* Unity 셰이더에 대한 코드 색 지정 
* Unity 설명서 액세스 

## <a name="xamarin"></a>Xamarin 

Xamarin 플랫폼 간 기능은 Xamarin Studio에서 항상 최고 수준의 기능이었지만 Mac용 Visual Studio에서만 사용할 수 있는 Xamarin 기능이 있습니다. 

### <a name="android"></a>Android 

* [Android SDK manager](https://developer.xamarin.com/guides/android/application_fundamentals/using-the-sdk-manager/)  
* Android O는 Mac용 Visual Studio에서만 지원되고 Xamarin Studio에서는 지원되지 않습니다. 

### <a name="ios-and-mac"></a>iOS 및 Mac 

* [iOS 서명 워크플로 업데이트](https://developer.xamarin.com/guides/cross-platform/macios/apple-account-management/) 
    * 서명 ID를 만들고 로컬 키 집합에 설치합니다. 
    * 프로비전 프로필을 만듭니다. 
    * 기존 프로필에 서명 ID를 추가합니다.
    *  장치 프로비전: Apple 개발자 포털에 장치를 등록하고 프로비전 프로필에 추가합니다.
* iOS 11, watchOS 4, tvOS 2는 Mac용 Visual Studio에서만 지원되고 Xamarin Studio에서는 지원되지 않습니다. 
* MacOS High Sierra는 Mac용 Visual Studio에서만 지원되고 Xamarin Studio에서는 지원되지 않습니다. 

### <a name="cross-platform"></a>플랫폼 간 

* [Xamarin Live Player](https://developer.xamarin.com/guides/cross-platform/live/)(**미리 보기**) 
* [Xamarin IoT](https://developer.xamarin.com/guides/cross-platform/iot/)(**미리 보기**) 
 