---
title: Xamarin을 사용한 모바일 개발에 대해 알아보기 | Microsoft 문서
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.prod: xamarin
ms.technology: xamarin-tools
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 921faa49690b641fda0e864d27705040a1b97f1e
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Xamarin을 사용한 모바일 개발에 대해 알아보기

이 문서에서는 Xamarin을 사용한 플랫폼 간 모바일 앱 개발을 이해하는 데 도움이 되는 몇 가지 개요가 나열되어 있습니다. 아직 Visual Studio 및 Xamarin을 설치하지 않았으면 먼저 [설정 및 설치](../cross-platform/setup-and-install.md) 프로세스를 시작하고 여기로 돌아와서 설치 관리자가 실행되는 동안 이러한 리소스를 살펴봅니다.  
  
> [!NOTE]
> 별도로 명시하지 않는 한, 처음에는 부수적인 페이지가 아닌 여기에 직접 연결된 페이지만 읽는 것이 좋습니다. 이 목록이 완료된 후에도 설치 프로세스가 계속 실행 중이면 돌아가서 추가 항목을 살펴볼 수 있습니다.  
>   
> 또한 "주요 사항"으로 표시된 항목을 자유롭게 검토한 후 나중에 "심층 분석" 항목을 확인합니다.  
  
## <a name="essentials-introduction-to-xamarin"></a>주요 사항: Xamarin 소개  

*10~20분*  
  
1.  [Xamarin을 사용한 Visual Studio의 모바일 앱](https://www.visualstudio.com/xamarin/)(visualstudio.com)에 Xamarin의 기본 특성에 대한 짧은 설명이 있습니다.  
  
2.  Xamarin 전문가인 James Montemagno와 함께하는[C# 및 Visual Studio를 사용하여 플랫폼 간 모바일 앱 빌드](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (영문)(Channel9, 15분 16초). 처음 3분은 Xamarin 개요이고 코드 데모가 뒤따릅니다.  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>주요 사항: Visual Studio 및 Xamarin 환경 개요  

*5~15분*  
  
-   Visual Studio 및 Xamarin이 설치된 Windows 컴퓨터에서 대부분의 작업을 수행합니다. 이 컴퓨터에서 직접 Windows 및 Android 앱을 빌드하고 데스크톱, 장치 또는 에뮬레이터에서 실행 및 디버그합니다. 또한 Mac을 통해 원격으로 iOS 앱을 빌드, 실행 및 디버그할 수 있습니다. Windows 컴퓨터의 Visual Studio를 iOS 스토리보드 디자이너 및 iOS 시뮬레이터에 연결할 수도 있습니다.  
  
-   Xcode 및 Mac용 Visual Studio가 설치된 Mac은 iOS 앱용 빌드 호스트, 서명 호스트 및 런타임 환경으로 사용됩니다. Windows 컴퓨터는 iOS 빌드를 이 Mac에 위임합니다. 응용 프로그램이 Mac의 iOS 시뮬레이터에서 또는 Mac에 연결된 테더링된 장치에서 직접 실행됩니다. Mac에서 앱과 상호 작용할 수 있지만 디버깅 환경은 Visual Studio에서 수행합니다.
  
이러한 관계는 아래에서 설명합니다.  
  
![Xamarin 환경에서 Windows 및 Mac 개발 컴퓨터 간의 관계](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin Learn 1")  

> [!NOTE]
> 이 다이어그램에는 완결성을 위한 Windows Phone이 나와 있습니다. Xamarin 플랫폼을 사용할 경우 권장되는 코드 공유 옵션은 .NET Standard 2.0 라이브러리입니다. 이는 Windows Phone 또는 Windows 10 Mobile 장치와 호환되지 않습니다. 

iOS 앱 작업에 대한 자세한 내용은 [Visual Studio용 Xamarin.iOS 소개](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/)를 참조하세요.
  
## <a name="essentials-how-projects-are-structured"></a>주요 사항: 프로젝트 구성 방법  

*10~30분*  
  
1.  [코드 공유 옵션](/xamarin/cross-platform/app-fundamentals/code-sharing/). 새 응용 프로그램의 경우 .NET Standard 라이브러리를 사용하여 코드를 공유할 수 있습니다. 데이터베이스 액세스, REST API 호출 및 이식 가능한 Xamarin 구성 요소 호출을 포함한 대부분 비즈니스 논리 코드는 .NET Standard 라이브러리에 있습니다. (이 문서의 끝에 있는 [심층 분석: Xamarin 구성 요소](#components)를 참조하세요.) 또한 Xamarin.Forms로 작성된 일반적인 UI 코드는 .NET Standard 라이브러리에 있습니다.  
  
2.  (선택 사항) [사례 연구: Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/)에서는 데이터, 데이터 액세스 및 비즈니스 계층을 구분하는 공유 코드에 대한 프로젝트 구조를 지정하는 것과 같은 전 기능 앱의 디자인 및 구조에 대한 몇 가지 모범 사례를 설명합니다.  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>주요 사항: 네이티브 및 Xamarin.Forms UI 계층  

*10~40분*  
  
Xamarin에서는 Xamarin Native 및 Xamarin.Forms의 두 가지 방법으로 뛰어난 앱을 빌드할 수 있습니다.  
  
Xamarin Native를 사용하여 iOS, Android 및 Windows 각 대상 플랫폼에 대한 별도의 UI 코드를 작성합니다.  이 방법을 사용하면 플랫폼별 API에 직접 액세스하여 플랫폼마다 사용자 지정된 UI 환경을 디자인할 수 있습니다.  각 플랫폼에 대한 기본 디자이너 및 컨트롤에 대해 모든 권한을 얻게 되므로 각 UI 구축에 도움이 됩니다.  
  
Xamarin.Forms는 모든 플랫폼에 대한 공유 UI 계층을 .NET Standard 라이브러리에 작성할 수 있는 일반화된 API 집합을 제공합니다.  Xamarin.Forms는 각 대상 플랫폼에 네이티브 컨트롤을 렌더링하여 네이티브 모양 및 느낌을 제공합니다.  디자이너를 사용하는 대신 C# 및 XAML을 사용하여 UI를 빌드할 수 있습니다.  

대부분의 개발자는 Xamarin.Forms를 사용합니다. 이는 Xamarin을 처음 접하는 개발자에게 권장되는 방법입니다. Xamarin Native 접근 방식은 더 어렵고 대상 플랫폼에 대한 더 자세한 지식이 필요합니다.
  
어떤 방법을 사용할지 고민할 필요가 없습니다. Xamarin Native와 Xamarin.Forms의 조합을 사용하여 앱을 구현할 수 있습니다.  
  
-   Xamarin.Forms를 사용하여 범용 화면을 빌드합니다. 이러한 화면은 로그인, 연락처 양식 및 검색 결과와 같이 플랫폼 간에 유사한 사용자 인터페이스 및 기능을 제공합니다.  
  
-   Xamarin.Forms의 다양한 사용자 지정 기능을 사용하여 플랫폼별 기준으로 UI를 조정합니다. 가장 간단한 사용자 지정 옵션에는 `OnPlatform` API가 포함됩니다. 또한 사용자 지정 보기를 만들고, 기존 렌더러를 확장하고, 사용자 지정 렌더러를 만들 수 있습니다.  
  
-   필요한 경우 Xamarin Native를 사용하여 각 플랫폼의 고유한 UI 기능을 사용하는 화면을 빌드할 수 있습니다. 한 가지 예로, 네이티브 카메라 캡처 및 이미지 조작을 사용하는 화면이 있습니다.  
  
일반적으로 먼저 플랫폼 간에 공유되는 UI 코드를 설정하는 Xamarin.Forms 솔루션으로 시작해야 합니다. 사용자 지정 기능을 사용하여 플랫폼별 조정을 수행합니다. 완전한 플랫폼별 화면이 필요한 경우 Xamarin Native를 사용하여 개별적으로 추가할 수 있습니다.  
  
자세히 알아보려면:  
  
1.  [Xamarin.Forms](/xamarin/xamarin-forms/)에서는 Xamarin.Forms와 네이티브 UI 레이어(Xamarin.iOS 및 Xamarin.Android) 간 장점 및 단점 비교와 간단한 개요를 제공합니다.  
  
2.  James Montemagno의 비디오 [Xamarin.Forms: Native iOS, Android & Windows apps with C# & XAML](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704)(Xamarin.Forms: C# 및 XAML을 이용한 네이티브 iOS, Android 및 Windows 앱)(Channel9, 13분 3초)에서 처음 3분은 또 다른 개요를 제공하고 데모를 계속 시청할 수 있습니다.  
  
3.  (선택 사항) [Xamarin.Forms 소개](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)  
  
4.  (선택 사항) [장치 클래스](/xamarin/xamarin-forms/platform/device/) 설명서에서 사용자 지정을 위해 `OnPlatform`을 사용하는 예제 참조
  
5.  (선택 사항) Jason Smith(MSDN Magazine)의 [크로스 플랫폼 - Xamarin.Forms를 사용하여 모바일 플랫폼 간에 UI 코드 공유](https://msdn.microsoft.com/magazine/dn904669.aspx)에서는 Xamarin.Forms 내의 다양한 사용자 지정 옵션에 대해 간략히 설명하며 자세한 내용은 [사용자 지정 렌더러](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/)에 나와 있습니다.  
  
## <a name="deeper-dive-debugging-with-emulators"></a>심층 분석: 에뮬레이터를 사용한 디버깅  

*10~15분*  
  
물리적 장치를 사용하지 않고도 플랫폼 간 앱을 디버깅하려면 다음에서 논의된 에뮬레이터를 사용해야 합니다.  
  
### <a name="microsofts-android-emulator"></a>Microsoft의 Android 에뮬레이터 

Visual Studio와 함께 설치되는 Microsoft의 [Visual Studio Emulator for Android](visual-studio-emulator-for-android.md)를 사용하는 것이 좋습니다.  [Visual Studio Emulator for Android](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) 비디오(영문)(Channel9, 5분 55초)에서는 개요 및 데모를 제공합니다.  
  
### <a name="apples-ios-simulator"></a>Apple의 iOS 시뮬레이터

자세한 내용은 [iOS 시뮬레이터 시작](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (영문)(apple.com)을 참조하세요.  
  
### <a name="microsofts-windows-phone-emulator"></a>Microsoft의 Windows Phone 에뮬레이터.

자세한 내용은 [Windows 10 Mobile용 Microsoft 에뮬레이터 테스트](/windows-uwp/windows-apps-src/debug-test-perf/test-with-the-emulator/)를 읽어 보세요.  
  
<a name="components" /> 

## <a name="deeper-dive-xamarin-components"></a>Deeper Dive: Xamarin Components  

*10분*  
  
Xamarin 구성 요소를 통해 대부분 확장 기능을 Xamarin 앱에 사용할 수 있습니다. 추가 UI 컨트롤, 인증, 다양한 클라우드 서비스(예: Microsoft Azure) 등을 비롯한 다운로드할 수 있는 전체 카탈로그는 [http://components.xamarin.com/](http://components.xamarin.com/)에서 찾을 수 있습니다.