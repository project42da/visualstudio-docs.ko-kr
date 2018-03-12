---
title: "Mac용 Visual Studio 소개 | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 3A130EC1-DD8C-4125-9034-B08D7AF7EA65
ms.openlocfilehash: d12331bd074f77db83ae4574195b8b6f7e5c452a
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="introducing-visual-studio-for-mac"></a>Mac용 Visual Studio 소개

Mac용 Visual Studio는 모바일, 데스크톱 및 웹 응용 프로그램을 만들기 위한 다양한 기능을 갖춘 정교한 최신 IDE입니다. 다음 개발을 지원합니다.

* .NET을 사용하는 모바일: Android, iOS, tvOS, watchOS
* Mac 데스크톱 앱
* .NET Core 응용 프로그램
* ASP.NET Core 웹 응용 프로그램
* 플랫폼 간 Unity 게임

고급 편집기, 디버깅, iOS, Mac 및 Android를 통한 네이티브 플랫폼 통합 및 통합 소스 제어와 같은 여러 기능을 포함하고 있습니다.

이 문서에서는 Mac용 Visual Studio의 다양한 섹션을 살펴보면서 플랫폼 간 응용 프로그램을 만들기 위한 강력한 도구를 구성하는 기능 중 일부를 안내하겠습니다.

## <a name="installation"></a>설치

Mac용 Visual Studio를 다운로드 및 설치하려면 [설치](~/installation.md) 가이드의 단계를 수행하세요.

## <a name="language-support"></a>언어 지원

Mac용 Visual Studio는 기본적으로 C# 및 F#에서의 개발을 지원합니다.

### <a name="c"></a>C#

C#은 Mac용 Visual Studio에서 플랫폼 간 응용 프로그램을 만들기 위한 가장 일반적으로 사용되는 언어입니다. IDE에는 모든 C# 7 기능에 대한 완벽한 지원이 포함됩니다.

### <a name="f"></a>F#

F#은 .NET에서 실행되도록 설계된 강력한 형식의 함수형 프로그래밍 언어입니다. Android, Mac 및 iOS 기반의 Mac용 Visual Studio 사용자가 프로그래밍 언어로 사용할 수 있습니다. F# 사용에 대한 자세한 정보 및 이 언어로 만든 샘플을 보려면 [F#](https://developer.xamarin.com/guides/cross-platform/fsharp/) 가이드를 방문하세요.

## <a name="platform-support"></a>플랫폼 지원

## <a name="net-core"></a>.NET Core

[.NET Core](https://www.microsoft.com/net/core#macos)는 Windows, Linux 및 Mac에서 실행되는 응용 프로그램을 만들기 위한 플랫폼입니다. Mac용 Visual Studio에서는 .NET Core 프로젝트의 로드, 생성, 실행 및 디버그를 지원합니다.

.NET Core 프로젝트를 실행하려면 .NET Core SDK를 다운로드 및 설치해야 합니다.

.NET Core 지원에는 다음이 포함됩니다.

* C# 및 F# IntelliSense
* 콘솔, 라이브러리 및 웹 응용 프로그램용 .NET Core 프로젝트 템플릿
* 중단점, 호출 스택, 조사식 창 등을 포함하는 전체 디버깅 지원
* NuGet PackageReferences 및 MSBuild 기반 복원
* .NET Core SDK에 포함된 Visual Studio 테스트 플랫폼을 사용하여 테스트를 실행 및 디버그하기 위한 통합 유닛 테스트 지원
* 이전 project.json 형식에서의 마이그레이션

시작하려면 ASP.NET Core 웹앱 [실습 교육](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started)을 확인하세요.

## <a name="xamarin"></a>Xamarin

최고 수준의 [Xamarin](https://developer.xamarin.com/) 지원을 통해 Android, macOS, iOS, tvOS 및 watchOS에 대한 풍부한 네이티브 환경을 개발할 수 있습니다. Xamarin.Forms 플랫폼 간 응용 프로그램은 네이티브 기능에 대한 액세스를 제한하지 않으면서 Android, iOS 및 macOS 간에 XAML 기반 UI 코드를 공유할 수 있도록 합니다.

시작하려면 모바일 앱 [실습 교육](https://github.com/Microsoft/vs4mac-labs/tree/master/Mobile/Getting-Started)을 확인하세요.

### <a name="android"></a>Android

Visual Studio에는 통합된 자체 Android SDK 관리자가 있습니다.

Android 응용 프로그램의 경우 Mac용 Visual Studio에는 Android `.axml` 파일과 함께 작동하여 사용자 인터페이스를 시각적으로 구성하는 자체 디자이너가 포함됩니다. Mac용 Visual Studio는 다음 이미지와 같이 Android Designer에서 이러한 파일을 엽니다.

![](media/intro-image31.png)

Android Designer에 대한 자세한 내용은 [디자이너 개요](https://developer.xamarin.com/Android/Guides/User_Interface/Designer_Overview) 문서를 참조하세요.

### <a name="ios"></a>iOS

iOS 디자이너는 Mac용 Visual Studio와 완벽하게 통합되었으며 .xib 파일 및 Storyboard 파일을 시각적으로 편집하여 iOS, tvOS, WatchOS UI 및 전환을 만들 수 있도록 합니다. 도구 상자와 Design Surface 간에 끌어서 놓기 기능을 사용하는 한편 직관적인 이벤트 처리 방식을 사용하여 전체 사용자 인터페이스를 빌드할 수 있습니다. iOS 디자이너는 디자인 타임 렌더링 기능이 추가된 [사용자 지정 컨트롤](https://developer.xamarin.com/guides/ios/user_interface/designer/ios_designable_controls_overview/)도 지원합니다.

![](media/intro-image30.png)

iOS 디자이너 사용에 대한 자세한 내용은 [디자이너](https://developer.xamarin.com/guides/ios/user_interface/designer) 문서를 참조하세요.

### <a name="mac"></a>Mac

Xamarin은 근사한 Mac 응용 프로그램을 만들 수 있도록 하는 기본 Mac API 바인딩을 제공합니다.

Mac용 Visual Studio에서 Mac 응용 프로그램을 작성하는 방법에 대한 자세한 내용은 [Xamarin.Mac](https://developer.xamarin.com/guides/#mac) 문서를 참조하세요.

## <a name="gaming"></a>게임

Mac용 Visual Studio는 Unity 5.6.1을 사용한 플랫폼 간 게임 개발에 대한 지원을 제공합니다.

시작하려면 Unity [실습 교육](https://github.com/Microsoft/vs4mac-labs/tree/master/Unity/Getting-Started)을 확인하세요.

## <a name="enterprise-features"></a>엔터프라이즈 기능

> [!Note]
> 이러한 제품은 Visual Studio Enterprise 구독에서만 사용할 수 있습니다.

### <a name="profiler"></a>프로파일러

Xamarin Profiler에는 프로파일링에 사용할 수 있는 세 가지 기기가 있습니다. [Xamarin Profiler 소개](https://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/xamarin-profiler/) 가이드에서는 이러한 기기가 무엇을 측정하는지 그리고 사용자 응용 프로그램을 어떻게 분석하는지 안내하고 각 화면에 표시되는 데이터의 의미를 설명합니다.

### <a name="inspector"></a>검사기

Xamarin Inspector는 도구가 포함된 대화형 C# 콘솔 도구를 사용자에게 제공하고, 라이브 응용 프로그램을 검사할 때 디버깅이나 진단 도구로 사용할 수 있을뿐만 아니라 강의 도구, 설명서 도구 또는 실험 도구로도 사용할 수 있습니다.

![](media/intro-inspector.png)

또한 Xamarin Inspector는 IDE의 디버깅 워크플로에 통합되고 다양한 프로그래밍 플랫폼(Android, iOS, Mac 및 Windows)을 대상으로 하는 고급 C# 콘솔을 제공하는 독립 실행형 응용 프로그램으로 구성됩니다.

자세한 내용은 [Xamarin Inspector](https://developer.xamarin.com/guides/cross-platform/inspector/) 가이드를 참조하세요.

## <a name="next-steps"></a>다음 단계

* **둘러보기 가져오기** - Mac용 Visual Studio의 주요 기능에 대한 개요를 얻으려면 Mac용 Visual Studio [IDE 둘러보기](~/ide-tour.md)를 참조하세요.
* **설치** - Visual Studio를 다운로드 및 설치하는 방법을 알아보려면 [설치](~/installation.md) 가이드를 참조하세요.
* **Xamarin 자습서** - Xamarin을 사용하여 코드를 개발하는 방법을 알아보려면 Xamarin [개발자 센터](https://developer.xamarin.com)로 이동하세요.
* **비디오** - Mac용 Visual Studio의 기타 기능 및 측면에 대해 자세히 알아보려면 [Xamarin University](https://university.xamarin.com) 웹 사이트에 있는 비디오를 시청하세요.
* **실습 교육** - Mac용 Visual Studio에 포함된 다양 한 작업을 시작하려면 [실습 교육](https://github.com/Microsoft/vs4mac-labs)을 확인하세요.