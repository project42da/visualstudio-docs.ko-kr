---
title: Xamarin 환경 확인 | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 862af0d8912811aee8e0110b48fa8cc3e8f1c06b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="verify-your-xamarin-environment"></a>Xamarin 환경 확인

설치 관리자가 완료되면( [Setup and install](../cross-platform/setup-and-install.md)참조) 몇 분 동안 Xamarin 개발을 경험할 모든 준비가 되었는지 확인하세요.  
  
 설치 확인을 완료했으면 다음 연습 중 하나 또는 모두를 시도합니다.  
  
-   Xamarin.Forms 응용 프로그램을 빌드하려면 [Visual Studio에서 Xamarin.Forms를 사용한 앱 빌드 기본 사항에 대해 알아보세요](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).
  
-   각 플랫폼에서 네이티브 사용자 인터페이스를 사용하되 .NET Standard 라이브러리의 일부 코드를 공유하려면 [Visual Studio에서 Xamarin을 사용하여 네이티브 UI로 앱을 빌드합니다](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md).
  
## <a name="all-platforms"></a>모든 플랫폼 
 
Visual Studio에서 먼저 **도구 > 확장 및 업데이트**를 선택하고 Xamarin 구성 요소를 업데이트해야 하는지 확인합니다.  
  
그런 다음, **파일 > 새 프로젝트**를 사용하여 Visual Studio에서 새 Xamarin.Forms 솔루션을 만듭니다. 대화 상자에서 **Visual C# > 플랫폼 간**을 확장하고 **모바일 앱(Xamarin.Forms)** 을 선택한 후, 확인을 클릭합니다. 이어지는 대화 상자에서 **비어 있는 앱**을 선택합니다. **코드 공유 전략**에서 **.NET Standard**를 선택합니다. 확인을 클릭합니다.

이러한 작업으로 공유 .NET Standard 2.0 라이브러리 프로젝트와 Android, iOS 및 UWP(유니버설 Windows 플랫폼)에 대한 응용 프로그램 프로젝트의 4개 프로젝트를 사용한 솔루션이 만들어집니다.  
  
![비어 있는 Xamarin.Forms 템플릿에서 새 프로젝트를 만들기의 결과](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin 확인 1")  
   
## <a name="android"></a>Android  
  
1. **도구 > Android > Android SDK 관리자**로 이동하여 최신 Android SDK 도구가 설치되어 있는지 확인합니다. 최신 버전의 Android SDK 도구, Android SDK 플랫폼 도구 및 Android SDK 빌드 도구를 설치합니다. 항상 최신 Android API 수준을 설치할 필요는 없습니다. 필요한 API 수준은 대상으로 지정할 플랫폼 수준에 따라 달라집니다. 일반적으로 Xamarin 플랫폼을 설치하면 필요한 Android 플랫폼 수준이 설치됩니다.  
  
2.  장치 또는 에뮬레이터에서 빌드 및 디버깅 확인:  
  
    -   솔루션 탐색기에서 Android 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
    -   도구 모음에서 사용 가능한 Android 장치 및 에뮬레이터 목록이 들어 있는 드롭다운이 표시되어야 합니다. 
    
    장치의 설정 페이지에 있는 개발자 옵션에서 Android 장치를 USB 디버깅에 대해 사용하도록 설정해야 합니다. 그런 다음, 장치가 USB 케이블을 통해 컴퓨터에 연결됩니다. 
    
    또한 목록은 에뮬레이터입니다. 장치 또는 Visual Studio 에뮬레이터 중 하나를 선택합니다.

  ![Visual Studio Emulator for Android를 디버그 대상으로 선택](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin Verify 3")  
  
  자세한 내용은 [Introducing Visual Studio's Emulator for Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx)(Visual Studio Emulator for Android 소개) (Visual Studio ALM 블로그)를 참조하세요. 에뮬레이터를 작동시키는 중 문제가 발생하면 [Troubleshooting the Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)을 참조하세요. **도구 > Android > Android Emulator 관리자**를 선택하여 에뮬레이터에 대한 새로운 장치 프로필을 만들 수도 있습니다.  
  
3. F5 키를 눌러 컴파일하고 프로그램을 Android 장치 또는 에뮬레이터에 배포합니다.
  
## <a name="windows"></a>Windows 
  
1.  솔루션 탐색기에서 유니버설 Windows 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  

2.  **솔루션 플랫폼** 드롭다운 목록에서 **x86** 또는 **x64**를 선택합니다. **로컬 컴퓨터**를 선택합니다.

3.  F5 키를 눌러 바탕 화면에 프로그램을 배포합니다.
  
## <a name="ios"></a>iOS  
  
1.  [Mac에 연결](/xamarin/ios/get-started/installation/windows/connecting-to-mac/)에 설명된 대로 Mac이 네트워크에서 사용 가능하고 Visual Studio와 연결되었는지 확인합니다.  
  
2.  솔루션 탐색기에서 iOS 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
3.  아래 표시된 대로 Visual Studio의 빌드 드롭다운에서 **iPhoneSimulator** 대상을 선택하거나 Mac에 테더링된 장치가 있는 경우 **iPhone** 대상을 선택합니다.   
  
 ![IPhoneSimulator 빌드 대상 선택](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin Verify 5") 

 시뮬레이터가 나열되지 않으면 Mac에서 Xcode를 시작하고 **Xcode > 기본 설정**을 선택한 후에 **다운로드**를 클릭합니다. **구성 요소** 제목에서 다운로드할 수 있는 시뮬레이터 버전이 표시되어야 합니다. 디버깅에 대한 추가 지침은 [iOS 디버깅](/xamarin/ios/deploy-test/debugging-in-xamarin-ios/?tabs=vsmac#Debugging_on_the_Simulator) 페이지에서 확인할 수 있습니다.
  
4.  Visual Studio 드롭다운에서 에뮬레이터 장치 대상을 선택합니다.

 ![iPhone 디버그 대상 선택](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin Verify 6")

5. F5 키를 눌러 디버거를 시작합니다. 앱을 조작할 Mac에서 시뮬레이터가 시작되고 동시에 Visual Studio에서 디버깅이 수행됩니다. 물리적 iPhone 또는 iPad가 Mac에 연결되어 있으면 여기에 나타나며, 해당 iPhone 또는 iPad를 대신 선택할 수 있습니다. 장치 또는 시뮬레이터가 나열되지 않으면 Mac에 대한 연결을 확인합니다. 위의 1단계에서 연결된 문서를 검토하거나 **도구 > iOS > Mac에 연결**로 이동합니다.  
  
6.  Mac에 연결할 때 문제가 발생하면 [연결 문제 해결](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/)을 읽어 보세요.  
  
7.  “No installed provisioning profiles match the installed iOS signing keys(설치된 프로비저닝 프로필이 설치된 iOS 서명 키와 일치하지 않습니다).”라는 오류가 표시되면 다음을 수행해 보세요.  
  
  - [Xcode에 사용자 계정 추가](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (영문)(apple.com)에 설명된 대로 Mac의 Xcode에 Apple Id 계정이 추가되어 있는지 확인합니다.  계정을 추가한 후 Visual Studio와 Xcode를 둘 다 다시 시작해야 합니다.  
    
  - iOS 번들 서명 탭의 iOS 프로젝트 속성에서 활성 디버그 구성을 위한 사용자 지정 권한 부여 필드가 비어 있는지 확인합니다.  참고: 위의 오류 메시지가 발생하는 경우에만 이 설정을 제거합니다.  
  
  ![CrossPlat Xamarin Verify 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin Verify 8")  
