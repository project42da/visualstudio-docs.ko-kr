---
title: 배포 개요-Visual Studio | Microsoft Docs
description: Visual Studio에서 앱을 배포 하기 위한 옵션에 대해 알아봅니다.
ms.custom: mvc
ms.date: 11/26/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0b21e8bf8abae2e5543d68751fd53b07778c8b3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>빠른 시작: Visual Studio에서 배포 시 소개

다른 컴퓨터, 장치, 서버 또는 클라우드에 설치할 수 있도록 응용 프로그램, 서비스 또는 구성 요소를 배포할 수 있습니다. Visual Studio에서 필요한 배포 유형에 적합한 방법을 선택할 수 있습니다. (다양 한 응용 프로그램 종류 명령줄 배포 또는 NuGet 같은 여기에 설명 되지 않은 다른 배포 도구를 지원 합니다.)

단계별 지침에 대 한 자습서를 참조 하십시오.

### <a name="deploy-to-local-folder"></a>로컬 폴더에 배포

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, 및 **.NET Core**: 게시 도구를 사용 하 여 로컬 폴더에 배포 되도록 합니다. 사용 가능한 옵션은 응용 프로그램 형식에 따라 달라 집니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**를 선택한 후 **폴더**합니다. 자세한 내용은 참조 [로컬 폴더에 배포](quickstart-deploy-to-local-folder.md)합니다.

    ![선택 게시](../deployment/media/quickstart-publish.png)

- **Visual c + + 런타임**: 로컬 배포 또는 정적 링크를 사용 하 여 Visual c + + 런타임을 배포할 수 있습니다. 자세한 내용은 참조 [네이티브 데스크톱 응용 프로그램 배포 (Visual c + +)](/cpp/ide/deploying-native-desktop-applications-visual-cpp)합니다. 

### <a name="publish-to-web-or-deploy-to-network-share"></a>네트워크 공유에 배포 또는 웹에 게시

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, 및 **.NET Core**: 게시 도구를 사용 하 여를 배포 하는 FTP 나 Web Deploy를 사용 하 여 웹 사이트입니다. 자세한 내용은 참조 [웹 사이트로 배포](quickstart-deploy-to-a-web-site.md)합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. 게시 도구에는 구성 단계에 따라 원하는 옵션을 선택 합니다.

    ![IIS, FTP 등을 선택 합니다.](../deployment/media/quickstart-publish-iis-ftp.png)

    ASP.NET 응용 프로그램 및 서비스는 여러 가지 다른 방법으로 배포할 수 있습니다. 자세한 내용은 참조 [배포 ASP.NET 웹 응용 프로그램 및 서비스](http://www.asp.net/aspnet/overview/deployment)합니다.

- **Visual c + + 런타임**: 중앙 배포를 사용 하 여 Visual c + + 런타임을 배포할 수 있습니다. 자세한 내용은 참조 [네이티브 데스크톱 응용 프로그램 배포 (Visual c + +)](/cpp/ide/deploying-native-desktop-applications-visual-cpp)합니다. 

- **Windows 바탕 화면** 웹 서버 또는 ClickOnce 배포를 사용 하 여 네트워크 파일 공유에는 Windows 데스크톱 응용 프로그램을 게시할 수 있습니다. 이렇게 하면 사용자가 클릭 한 번으로 응용 프로그램을 설치할 수 있습니다. 자세한 내용은 참조 [ClickOnce를 사용 하 여 데스크톱 응용 프로그램 배포](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) 및 [ClickOnce를 사용 하는 네이티브 앱을 배포할](/cpp/ide/clickonce-deployment-for-visual-cpp-applications)합니다.

### <a name="publish-to-azure"></a>Azure에 게시

- **ASP.NET, ASP.NET Core, Python, Node.js, 및.NET Core** 웹 응용 프로그램: Azure 앱 서비스 또는 Azure 가상 컴퓨터를 신속 하 게 앱을 배포 하려면 게시 도구를 사용할 수 있습니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. 게시 대화 상자에서 선택 하거나 **Microsoft Azure 앱 서비스** 또는 **Microsoft Azure 가상 컴퓨터**, 한 다음 구성 단계를 따릅니다.

    ![Azure 앱 서비스 선택](../deployment/media/quickstart-publish-azure.png "Azure 앱 서비스 선택")

    Azure 가상 컴퓨터에를 게시 하려면 오른쪽 스크롤하여 선택 **Microsoft Azure 가상 컴퓨터**합니다.

    간략 한 소개를 참조 하십시오. [Azure에 게시](quickstart-deploy-to-azure.md)합니다. 참고: [ASP.NET Core 응용 프로그램을 Azure에 게시](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다. Git를 사용 하 여 배포를 참조 하십시오. [Git 사용 하 여 Azure에 ASP.NET Core의 연속 배포](/aspnet/core/publishing/azure-continuous-deployment)합니다.

    > [!NOTE]
    > Azure 계정이 아직 없는 경우 다음을 할 수 있습니다 [여기 등록](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)합니다.

- 다른 **Azure 서비스**: 특정 참조 [Azure 서비스](/azure/#pivot=products) Visual Studio에서 지원 될 수 있는 다양 한 배포 옵션에 대 한 설명서입니다.

### <a name="publish-to-microsoft-store"></a>Microsoft 스토어에 게시

Visual Studio에서 Microsoft 저장소에 배포에 대 한 응용 프로그램 패키지를 만들 수 있습니다.

- **UWP**: 앱 패키지를 메뉴 항목을 사용 하 여 배포할 수 있습니다. 자세한 내용은 참조 [Visual Studio를 사용 하 여 UWP 앱을 패키지](/windows/uwp/packaging/packaging-uwp-apps)합니다.

    ![응용 프로그램 패키지 만들기](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows 바탕 화면**: Visual Studio 2017 15.4 버전부터 데스크톱 브리지를 사용 하 여 Microsoft 저장소를 배포할 수 있습니다. 이렇게 하려면 먼저 Windows 응용 프로그램 패키징 프로젝트를 만듭니다. 자세한 내용은 참조 [Microsoft 저장소 (데스크톱 브리지)에 대 한 데스크톱 응용 프로그램 패키지](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)합니다.

    ![데스크톱 브리지](../deployment/media/feature-tour-desktop-bridge.png)

### <a name="create-an-installer-package-windows-client"></a>프로그램 설치 관리자 패키지 (Windows 클라이언트) 만들기

- MSI 기반 WiX 설치 관리자를 사용 하 여 만들 수 있습니다는 [WiX 도구 집합 Visual Studio 2017 확장](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)합니다.

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements) Flexera 소프트웨어에서 Visual Studio 2017 (Community Edition을 지원 되지 않습니다.) 함께 사용할 수 있습니다. InstallShield Limited Edition은 더 이상 Visual Studio와 함께 포함 하 고 Visual Studio 2017;에서 지원 되지 않습니다. 문의 [Flexera 소프트웨어](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) 이후 가용성에 대 한 합니다.

- 설치 프로젝트 (vdproj)를 만들려는 경우 설치는 [Visual Studio 2017 설치 관리자 프로젝트 확장](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview)합니다.

- 부트스트래퍼 라고 일반 설치 관리자를 구성 하 여 데스크톱 응용 프로그램에 대 한 필수 구성 요소를 설치할 수 있습니다. 자세한 내용은 참조 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)합니다.

### <a name="deploy-to-test-lab"></a>테스트 랩에 배포

보다 정교한 개발 및 가상 환경에 응용 프로그램을 배포 하 여 테스트를 사용할 수 있습니다. 자세한 내용은 참조 [랩 환경에서 테스트](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md)합니다.

### <a name="devops-deployment"></a>DevOps 배포

팀 환경에서 응용 프로그램의 연속 배포를 사용 하려면 Visual Studio Team Services VSTS ()를 사용할 수 있습니다. 자세한 내용은 참조 [빌드 및 릴리스](/vsts/build-release/index) 및 [Azure에 배포](/vsts/deploy-azure/index)합니다.

### <a name="deployment-for-other-app-types"></a>다른 응용 프로그램 종류에 대 한 배포

| 앱 형식 | 배포 시나리오 | 링크 |
| --- | --- | --- |
| **Office 응용 프로그램** | Visual Studio에서 Office 용 추가 기능을 게시할 수 있습니다. | [배포 및 Office 추가 기능을 게시합니다](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF 또는 OData 서비스**  | 다른 응용 프로그램 웹 서버에 배포 하는 WCF RIA 서비스를 사용할 수 있습니다. | [개발 및 WCF Data Services 배포](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch는 Visual Studio 2017에서 더 이상 지원 하지만 및 이전 버전 Visual Studio 2015에서 구축할 수 없습니다. | [LightSwitch 응용 프로그램 배포](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

