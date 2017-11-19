---
title: "응용 프로그램, 서비스 및 구성 요소 배포 | Microsoft Docs"
ms.custom: 
ms.date: 07/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET applications, deploying
- components [Visual Studio], deploying
- installers
- publishing
- deploying applications [Visual Studio]
- deploying applications [Visual Studio], about deploying applications
- components [.NET Framework], deploying
ms.assetid: 63fcdd5b-2e54-4210-9038-65bc23167725
caps.latest.revision: "33"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 9d9aeaa80aa054b8178adbfc707b1537449776d7
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="deploying-applications-services-and-components"></a>응용 프로그램, 서비스 및 구성 요소 배포

다른 컴퓨터, 장치, 서버 또는 클라우드에 설치할 수 있도록 응용 프로그램, 서비스 또는 구성 요소를 배포할 수 있습니다. Visual Studio에서 필요한 배포 유형에 적합한 방법을 선택할 수 있습니다.  
  
다음 표에서 다양 한 배포 시나리오에 설명 하 고 각 시나리오에 대 한 자세한 정보에 대 한 링크를 제공 합니다.  

Windows 앱에 대 한 설치 환경을 만들 수 있는 옵션의 논의 알려면 [유니버설 Windows 플랫폼 (UWP) 브리지에 데스크톱](/windows/uwp/porting/desktop-to-uwp-root#convert)합니다.

 
## <a name="in-this-section"></a>단원 내용  
  
| 배포 시나리오 | 지원 내용 |
| --- | --- |  
| **클라우드에 게시:** 가능 응용 프로그램, 서비스 및 데이터에서 사용할 수 있는 Visual Studio를 사용 하 여 Microsoft Azure에 배포 하 여 모든 위치입니다.|[Microsoft Azure에 응용 프로그램 게시](http://msdn.microsoft.com/library/windowsazure/ee460772.aspx) |
| **Windows 앱 게시:** 쉽게 빌드을 제출 하 고 수 전 세계 여러 고객에 게 Microsoft 스토어에서 앱을 판매 합니다. |[Windows 앱을 게시](https://developer.microsoft.com/store/publish-apps) |
| **ASP.NET 응용 프로그램 또는 서비스 배포:** 여러 가지 다른 방법으로 ASP.NET 응용 프로그램 및 서비스를 배포할 수 있습니다.|[ASP.NET 웹 응용 프로그램 및 서비스 배포](http://www.asp.net/aspnet/overview/deployment) |
| **Office 용 추가 기능에 게시:** for Visual Studio에서 Office 추가 기능을 게시할 수 있습니다. | [배포 및 Office 추가 기능을 게시합니다](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF 또는 OData 서비스 배포:** 다른 응용 프로그램 웹 서버에 배포한 WCF RIA 서비스를 사용할 수 있습니다. | [개발 및 WCF Data Services 배포](https://docs.microsoft.com/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **데스크톱 응용 프로그램 배포:** ClickOnce 배포를 사용 하 여 웹 서버 또는 네트워크 파일 공유에는 데스크톱 응용 프로그램을 게시할 수 있습니다. 이렇게 하면 사용자가 클릭 한 번으로 응용 프로그램을 설치할 수 있습니다. | [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md) |
| **Visual c + + 응용 프로그램 배포:** 중앙 배포, 로컬 배포 또는 정적 링크를 사용 하 여 응용 프로그램과 함께 Visual c + + 런타임을 배포할 수 있습니다. | [네이티브 데스크톱 응용 프로그램 배포(Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp.md) |
| **설치 관리자를 만들려면:** MSI 기반 WiX 설치 관리자를 사용 하 여 만들 수 있습니다는 [WiX 도구 집합 Visual Studio 2017 확장](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)합니다. InstallShield Limited Edition은 더 이상 Visual Studio;에 포함된 문의 [Flexera 소프트웨어](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) Visual Studio 2017에 대 한 가용성에 대 한 합니다. |
| **테스트를 위해 응용 프로그램 배포:** 보다 정교한 개발 및 테스트 가상 환경에 응용 프로그램을 배포 하 여 설정할 수 있습니다.|[랩 환경에서 테스트](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md) | 
| **필수 구성 요소 설치:** 부트스트래퍼 라고 일반 설치 관리자를 구성 하 여 데스크톱 응용 프로그램에 대 한 필수 구성 요소를 설치할 수 있습니다.|[응용 프로그램 배포 필수 조건](../deployment/application-deployment-prerequisites.md) |
| **LightSwitch 응용 프로그램 또는 서비스 배포:** LightSwitch는 Visual Studio 2017에서 더 이상 지원 하지만 및 이전 버전 Visual Studio 2015에서 구축할 수 없습니다. | [LightSwitch 응용 프로그램 배포](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) |  
