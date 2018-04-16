---
title: Visual Studio 및 Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
caps.latest.revision: 10
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: be1739a83e05ca55fa288fa707b37fddb095cc57
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2018
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio 및 Xamarin

Xamarin은 일반적인 C#/.NET 코드 베이스에서 네이티브 iOS, Android 및 Windows 앱을 빌드하기 위한 모바일 앱 개발 플랫폼입니다. Xamarin으로 작성된 앱은 플랫폼 간에 75%에서 거의 100%까지 코드를 재사용할 수 있습니다. 이러한 앱은 기본 플랫폼 API에 대한 모든 액세스 권한이 있으며 네이티브 사용자 인터페이스를 통합할 수 있습니다. 런타임 성능에 거의 영향이 없는 플랫폼별 패키지에 컴파일됩니다. 참고: Xamarin도 F#을 지원하지만 이 설명서에서는 C#에 대해서만 중점적으로 설명합니다. Visual Basic은 현재 지원되지 않습니다.  
  
C#, .NET 및 Visual Studio에 익숙한 개발자는 모바일 앱용 Xamarin으로 작업할 때와 동일한 성능과 생산성을 이용할 수 있습니다. 이러한 이점에는 Objective-C 또는 Java와 같은 네이티브 코딩 언어를 배울 필요 없이 Android, iOS 및 Windows 장치에서 원격 디버깅이 가능하다는 것도 포함됩니다. 따라서 NASCAR, Aviva 및 MixRadio와 같은 뛰어난 사용자 인터페이스를 가진 많은 고성능 앱이 Xamarin을 사용하여 빌드되었다는 점은 그리 놀랄 일이 아닙니다.  
  
이 설명서를 참조하여 이러한 환경을 빌드하기 위한 **Xamarin이 포함된 Visual Studio**의 전체 기능을 살펴볼 수 있습니다.  
  
-   약간 시간(인터넷 연결 속도, 이미 설치한 항목 및 선택할 옵션에 따라 일반적으로 2~4시간)이 걸리는 프로세스인 [Setup and install](../cross-platform/setup-and-install.md)부터 시작합니다.  
  
-   설치 관리자를 실행하는 동안 [Xamarin을 사용한 모바일 개발에 대해 알아보기](learn-about-mobile-development-with-xamarin.md)를 살펴볼 수 있습니다. 여기서는 Xamarin의 특성, Xamarin.Forms와 네이티브 UI를 비교한 내용 등이 제공됩니다.  
  
-   설치가 완료되면 [Xamarin 환경 확인](../cross-platform/verify-your-xamarin-environment.md)을 수행합니다.  
  
-   그리고 마지막으로 [Visual Studio에서 Xamarin.Forms를 사용한 앱 빌드 기본 사항 알아보기](/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md) 자습서를 진행합니다.  
  
[모든 Visual Studio 2017 버전](https://www.visualstudio.com/vs)(Community, Professional 및 Enterprise)을 사용하여 모든 Xamarin 기능으로 작업할 수 있습니다. 별도의 라이선스는 필요하지 않습니다.  
  
> [!NOTE]
>  이러한 지침에서는 Windows 및 Visual Studio에 친숙한 개발자를 위해 가장 간편하고 직관적인 컴퓨터 구성을 설명합니다. 이 구성에서는 Mac과 상호 작용하여 iOS 시뮬레이터와 테더링된 장치를 사용하면 되므로 전체 개발 환경이 간소화됩니다. Mac에 친숙한 경우에는 Parallels 또는 VMWare 내부에서 Visual Studio를 실행하거나 Mac용 Visual Studio를 사용하는 것이 좋습니다. 관련 지침은 [Mac 사용자용 설정, 설치 및 확인](../cross-platform/setup-install-and-verifications-for-mac-users.md)을 참조하세요.  
  
> [!NOTE]
>  HTML 및 CSS 기반 플랫폼 간 개발 솔루션을 사용하려는 경우에는 [Visual Studio에서 플랫폼 간 개발](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML)에 설명되어 있는 Visual Studio Tools for Apache Cordova를 확인하세요.