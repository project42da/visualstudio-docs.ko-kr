---
title: "UWP(유니버설 Windows 플랫폼)용 앱 개발 | Microsoft 문서"
ms.custom: 
ms.date: 10/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eac59cb6-f12e-4a77-9953-6d62b164a643
caps.latest.revision: "48"
author: stevehoag
ms.author: shoag
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: a696a0b827cc8fe367390efbba01c2a18ff178bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="develop-apps-for-the-universal-windows-platform-uwp"></a>UWP(유니버설 Windows 플랫폼)용 앱 개발
유니버설 Windows 플랫폼과 단일 Windows 코어를 사용하여 휴대폰에서 데스크톱에 이르는 모든 Windows 10 장치에서 동일한 앱을 실행할 수 있습니다. Visual Studio 및 유니버설 Windows 앱 개발 도구를 사용하여 이러한 유니버설 Windows 앱을 만듭니다.  
  
 ![유니버설 Windows 플랫폼](../cross-platform/media/uwp_coreextensions.png "UWP_CoreExtensions")  
  
 Windows 10 Phone, Windows 10 데스크톱 또는 Xbox에서 이 앱을 실행합니다. 동일한 앱 패키지입니다. Windows 10 단일 통합 코어가 도입되면서 하나의 앱 패키지를 모든 플랫폼에서 실행할 수 있습니다. 일부 플랫폼에는 플랫폼 특정 동작을 활용하기 위해 앱에 추가할 수 있는 확장 SDK가 있습니다. 예를 들어 모바일용 SDK 확장은 Windows Phone에서 뒤로 단추를 누르는 동작을 처리합니다. 프로젝트에서 확장 SDK를 참조하는 경우 런타임 검사를 추가하여 해당 플랫폼에서 SDK를 사용할 수 있는지 테스트하면 됩니다. 이런 방식으로 각 플랫폼에 동일한 앱 패키지를 사용할 수 있습니다.  
  
 **Windows Core란 무엇인가요?**  
  
 처음으로 Windows가 모든 Windows 10 플랫폼에서 공통 코어를 사용하도록 리팩터링되었습니다. 하나의 공통 소스, 하나의 공통 Windows 커널, 하나의 파일 I/O 스택 및 하나의 앱 모델이 있습니다. UI의 경우 하나의 XAML UI 프레임워크와 하나의 HTML UI 프레임워크가 있습니다. 다양한 Windows 10 장치에서 앱을 쉽게 실행할 수 있으므로 뛰어난 앱을 개발하는 데만 집중할 수 있습니다.  
  
 **유니버설 Windows 플랫폼이란 정확히 무엇인가요?**  
  
유니버설 Windows 플랫폼은 단순히 계약 및 버전의 모음입니다. 앱을 실행할 수 있는 대상을 지정하는 데 사용됩니다. 더 이상 운영 체제를 대상으로 지정하지 않습니다. 이제 하나 이상의 장치 제품군을 대상으로 지정합니다. 자세한 내용은 [유니버설 Windows 플랫폼 개요](/windows/uwp/get-started/universal-application-platform-guide)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 유니버설 Windows 앱 개발 도구에는 여러 다른 장치에서 앱 모양을 확인하는 데 사용할 수 있는 에뮬레이터가 제공됩니다. 이러한 에뮬레이터를 사용하려는 경우 물리적 컴퓨터에서 이 소프트웨어를 설치해야 합니다. 물리적 컴퓨터는 Windows 8.1(x64) Professional Edition 이상을 실행하고 클라이언트 Hyper-V 및 SLAT(두 번째 수준 주소 변환)를 지원하는 프로세서가 있어야 합니다. Visual Studio가 가상 컴퓨터에 설치된 경우에는 에뮬레이터를 사용할 수 없습니다.  
  
 필요한 소프트웨어 목록은 다음과 같습니다.  
  
-   [Windows 10](http://windows.microsoft.com/windows/downloads) - Visual Studio 2017은 Windows 10에서만 UWP 개발을 지원합니다. 자세한 내용은 Visual Studio [플랫폼 대상 지정](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs) 및 [시스템 요구 사항](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)을 참조하세요.   
  
-   [Visual Studio](https://www.visualstudio.com/downloads/) - 선택적인 유니버설 Windows 플랫폼 개발 워크로드도 필요합니다.  

     ![UWP 워크로드](media/uwp_workload.png)
  
이 소프트웨어를 설치한 후에 개발을 위해 Windows 10 장치를 사용하도록 설정해야 합니다. 자세한 내용은 [장치를 개발에 사용하도록 설정](/windows/uwp/get-started/enable-your-device-for-development)을 참조하세요. 각 Windows 10 장치에 대한 개발자 라이선스는 더 이상 필요하지 않습니다.  
    
## <a name="universal-windows-apps"></a>유니버설 Windows 앱  
C#, Visual Basic, C++ 또는 JavaScript에서 기본 설정된 개발 언어를 선택하여 Windows 10 장치용 유니버설 Windows 플랫폼 앱을 만듭니다. [첫 번째 앱 만들기](/windows/uwp/get-started/your-first-app)를 참조하거나 [Windows 10용 도구 개요](http://channel9.msdn.com/Series/ConnectOn-Demand/229) 비디오를 시청하세요.
  
기존 Windows 스토어 8.1 앱, Windows Phone 8.1 앱 또는 Visual Studio 2015를 사용하여 만든 유니버설 Windows 앱이 있으면 이러한 앱을 포팅하여 최신 유니버설 Windows 플랫폼을 사용해야 합니다. [Windows 런타임 8.x에서 UWP로 이동](/windows/uwp/porting/w8x-to-uwp-root)을 참조하세요.
  
유니버설 Windows 앱을 만든 후 앱을 패키지하여 Windows 10 장치에 설치하거나 Windows 스토어에 제출해야 합니다. [앱 패키징](/windows/uwp/packaging/index)을 참조하세요.

## <a name="see-also"></a>참고 항목
[Visual Studio에서 플랫폼 간 모바일 개발](../cross-platform/cross-platform-mobile-development-in-visual-studio.md)  
