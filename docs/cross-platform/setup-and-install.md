---
title: Visual Studio용 Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 8ae03dfe4ed2e72015ca1f7d91153d862f44ce40
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="setup-and-install"></a>설정 및 설치

Xamarin을 사용하여 일반적인 C#/.NET 코드 베이스에서 네이티브 iOS, Android 및 Windows 앱을 빌드하려면 다음 하드웨어 및 소프트웨어가 필요합니다.

-   Windows 및 Android 앱 작업의 경우: Visual Studio 2017(Xamarin 개발 기능 포함)이 설치된 Windows 개발 컴퓨터(가상 머신 아님).  

-   iOS 앱 작업의 경우: Xcode 및 가 Mac용 Visual Studio가 설치된 macOS Sierra 10.12 이상 버전의 Mac.

Xamarin 플랫폼을 사용하기 위해 별도 라이선스가 필요하지는 않습니다.
 
Windows 및 Mac 컴퓨터를 동시에 설정할 수 있고 해당 설치 관리자가 실행되는 동안 [Xamarin을 사용한 모바일 개발에 대해 알아보기](../cross-platform/learn-about-mobile-development-with-xamarin.md)를 검토하여 필요한 배경 자료를 읽고 살펴볼 수 있습니다.

이 설정 및 설치를 수행한 후 Xamarin 플랫폼을 사용하는 데 문제가 있으면 [forums.xamarin.com](http://forums.xamarin.com/)에 질문을 게시하세요.

<a name="prereq" /> 

## <a name="pre-requisites"></a>필수 구성 요소

###  <a name="for-targeting-windows-and-android"></a>Windows 및 Android 타기팅

Visual Studio 2017을 설치하기 위한 자세한 필수 구성 요소는 [Visual Studio 2017 제품군 시스템 요구 사항](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)을 참조하세요.

모든 업데이트가 설치되어 있는 Windows 10을 실행 중인 물리적 Windows 컴퓨터(가상 머신 아님)에 Visual 2017을 설치합니다. 

### <a name="for-targeting-ios"></a>iOS 타기팅

Windows 컴퓨터의 장치 또는 iOS 에뮬레이터를 대상으로 지정하려면 macOS 10.12 이상 및 Xcode 8.3을 실행 중인 네트워크로 연결된 Mac 또는 Mac 미니가 필요합니다. 더 자세한 요구 사항은 [Mac용 Visual Studio 설정 및 설치](/visualstudio/mac/installation.md)를 참조하세요.

<a name="windows" /> 

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Windows 설치(Visual Studio 및 Xamarin)

Visual Studio 2017을 아직 설치하지 않은 경우 다음 단계를 수행합니다.

1.  [어떤 버전이든 Visual Studio 2017 설치 관리자를 다운로드하여 설치합니다](https://www.visualstudio.com/downloads/)(Community, Professional 또는 Enterprise). Visual Studio 2017 Community는 무료 버전입니다. Professional 및 Enterprise 버전은 30일 동안 평가판으로 사용할 수 있으며 이후에는 라이선스가 필요합니다.

2.  **설치** 대화 상자가 나타나면 다음 상자를 선택합니다.    

    - **모바일 및 게임 > .NET을 사용한 모바일 개발** 이 옵션은 다양한 Android 도구와 소프트웨어 개발 키트를 자동으로 선택합니다. 

        ![게임 및 모바일 개발에서 모바일 개발 옵션 선택](../cross-platform/media/cross-plat-xamarin-setup-2a.png "Cross-Plat Xamarin Setup 2")

    - (선택 사항) **Windows > 유니버설 Windows 플랫폼 개발** 

이미 Visual Studio 2017을 설치했으나 Xamarin 플랫폼은 아직 설치하지 않은 경우 다음 단계를 수행합니다.

1. **시작** 메뉴에서 **Visual Studio 설치 관리자**를 실행합니다.

2.  설치 관리자 내에서 **추가** 단추를 클릭한 다음, **수정**을 선택합니다.

    ![Visual Studio 설치에서 수정 옵션 선택](../cross-platform/media/cross-plat-xamarin-setup-1a.png "Cross-Plat Xamarin Setup 1")

3.  **설치** 대화 상자가 나타나면 **모바일 및 게임 > .NET을 사용한 모바일 개발** 및 (선택 사항) **Windows > 유니버설 Windows 플랫폼 개발**을 선택합니다. **.NET을 사용한 모바일 개발** 옵션은 기존 Xamarin 설치도 업데이트합니다.

설치가 실행되는 동안 Mac 설치 지침을 계속 진행하고 [Xamarin을 사용한 모바일 개발에 대해 알아보기](../cross-platform/learn-about-mobile-development-with-xamarin.md)를 살펴볼 수 있습니다.

5.  설치가 완료되면 Visual Studio를 시작하고 메시지가 표시되면 Microsoft 계정으로 로그인합니다. 이 계정은 Windows에서 사용하는 것과 동일한 계정입니다.

6.  Android 앱을 테스트할 경우 물리적 Android 장치가 없으면 [Android SDK 에뮬레이터](/xamarin/android/get-started/installation/android-emulator/)를 사용합니다. 

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Mac 설치(Apple ID, Xcode 및 Xamarin)

1.  Apple ID가 없으면 [https://appleid.apple.com](https://appleid.apple.com/)에서 무료 Apple ID를 만듭니다. 이 Apple ID는 Xcode를 설치하고 서명하는 데 필요합니다.

2.  [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/)에서 Xcode를 다운로드하여 설치하고, [Adding Your Account to Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1)(XCode에 계정 추가) (apple.com)에 설명된 대로 Apple ID를 추가합니다.

3.  [Mac용 Visual Studio 설정 및 설치](/visualstudio/mac/installation.md)에 있는 지침에 따라 Mac용 Visual Studio를 다운로드하고 설치합니다.

4.  Windows 및 Mac 컴퓨터 모두에서 Xamarin 설치를 마쳤으면 Windows 컴퓨터의 Visual Studio에서 iOS 및 Mac 작업을 수행할 수 있도록 [Connecting to the Mac](/xamarin/ios/get-started/installation/windows/connecting-to-mac/)(Mac에 연결) (xamarin.com)의 지침을 따릅니다.

두 컴퓨터는 모두 같은 로컬 네트워크에 있어야 합니다.