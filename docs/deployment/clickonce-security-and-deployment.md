---
title: "ClickOnce 보안 및 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployment
- deploying applications [ClickOnce]
- ClickOnce deployment
- publishing, ClickOnce
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
caps.latest.revision: "32"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 7e56d596c37960ddfa548921da897f08fbfbbf5b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="clickonce-security-and-deployment"></a>ClickOnce 보안 및 배포
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]설치 하 고 최소한의 사용자 작업으로 실행할 수 있는 자동 업데이트 Windows 기반 응용 프로그램을 만들 수 있게 해 주는 배포 기술이입니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]게시 하 고 Visual Basic 및 C#를 사용 하 여 프로젝트를 개발한 경우 ClickOnce 기술을 사용 하 여 배포 된 응용 프로그램 업데이트에 대 한 완벽 한 지원을 제공 합니다. Visual C++ 응용 프로그램을 배포 하는 방법에 대 한 내용은 [Visual C++ 응용 프로그램에 대 한 ClickOnce 배포](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]배포 배포의 세 가지 주요 문제를 극복 합니다.  
  
-   **응용 프로그램 업데이트의 어려움입니다.** Microsoft Windows Installer 배포를 사용 하 여 응용 프로그램이 업데이트 될 때마다 사용자는 msp 파일 업데이트를 설치 하는; 설치 된 제품에 적용 사용 하 여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 업데이트를 자동으로 제공할 수 있습니다. 응용 프로그램의 변경 된 부분만 다운로드 되 고 병렬 하 여 새 폴더에서 업데이트 된 전체 응용 프로그램이 다시 설치 됩니다 다음.  
  
-   **사용자의 컴퓨터에 영향을 미칩니다.** Windows Installer 배포를 사용 하 여 응용 프로그램이 자주 사용 공유 구성 요소를 프로그램과 충돌할 수 없습니다. 사용 하 여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 경우 각 응용 프로그램은 독립적 이며 다른 응용 프로그램을 방해할 수 있습니다.  
  
-   **보안 권한입니다.** Windows Installer 배포 관리자 권한이 필요 하며 제한 된 사용자 설치만. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 설치를 사용 하면 비관리 응용 프로그램에 필요한 코드 액세스 보안 권한만 부여 하 고 있습니다.  
  
 과거 이러한 문제로 인해 개발자는, 쉽게 설치 하기 위해 풍부한 인터페이스를 포기 하면서 Windows 기반 응용 프로그램 대신 웹 응용 프로그램을 만들 수 있습니다. 사용 하 여 배포 된 응용 프로그램을 사용 하 여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], 두 기술 모두 가장 적합 있을 수 있습니다.  
  
## <a name="what-is-a-clickonce-application"></a>ClickOnce 응용 프로그램 이란?  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] (.xbap) Windows Presentation Foundation, Windows Forms (.exe), 콘솔 응용 프로그램 (.exe) 또는 Office 솔루션 (.dll)를 사용 하 여 게시 된 응용 프로그램은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기술. 게시할 수 있는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 세 가지 방법으로 응용 프로그램: 웹 페이지, 네트워크 파일 공유 또는 CD-ROM과 같은 미디어. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 최종 사용자의 컴퓨터에 설치 하 고 컴퓨터가 오프 라인 상태 또는 아무것도 최종 사용자의 컴퓨터에 영구적으로 설치 하지 않고 온라인 전용 모드로 실행할 수 있습니다 경우에 로컬로 실행할 수 있습니다. 자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하세요.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램 자체 업데이트 될 수 있습니다; 사용할 수 있게 되 고 자동으로 업데이트 된 파일을 대체 하는 새 버전에 대 한 확인할 수 있습니다. 개발자는 업데이트 동작; 지정할 수 있습니다. 네트워크 관리자가 제어할 수 업데이트 전략, 예를 들어, 업데이트가 필수로 표시 합니다. 업데이트 수 롤백할 수도 이전 버전으로 최종 사용자 또는 관리자입니다. 자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 때문에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 격리 된 설치 하거나 실행 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 해도 기존 응용 프로그램입니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램은 독립적인 경우. 각 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 설치 되어 안전한 사용자별, 응용 프로그램별 캐시에서에서 실행 됩니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램은 인터넷 또는 인트라넷 보안 영역에서 실행 합니다. 필요한 경우 응용 프로그램이 승격 된 보안 권한을 요청할 수 있습니다. 자세한 내용은 [ClickOnce 응용 프로그램 게시](../deployment/securing-clickonce-applications.md)를 참조하세요.  
  
## <a name="how-clickonce-security-works"></a>ClickOnce 보안 작동 방법  
 코어 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 보안은 인증서, 코드 액세스 보안 정책 및 ClickOnce 신뢰 프롬프트에 기초 합니다.  
  
### <a name="certificates"></a>인증서  
 Authenticode 인증서는 응용 프로그램 게시자의 신뢰성을 확인 하는 데 사용 됩니다. 응용 프로그램 배포에 Authenticode를 사용 하면 ClickOnce에서 규정 되 고 신뢰할 수 있는 소스에서 가져온 올바른 프로그램으로 유해한 프로그램을 방지 합니다. 필요에 따라 응용 프로그램을 서명할 인증서도 사용할 수와 배포 매니페스트 파일이 변조 된 증명 하기 위해. 자세한 내용은 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md). 인증서를 신뢰할 수 있는 게시자 목록을 보유 하도록 클라이언트 컴퓨터를 구성 하려면 사용할 수도 있습니다. 응용 프로그램 게시자를 신뢰할 수 있는 경우, 사용자 개입 없이 설치할 수 있습니다. 자세한 내용은 [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md)을 참조하십시오.  
  
### <a name="code-access-security"></a>코드 액세스 보안  
 코드 액세스 보안 코드는 보호 된 리소스에 액세스를 제한할 수 있습니다. 대부분의 경우에서 사용 권한을 제한 하 여 인터넷 또는 로컬 인트라넷 영역을 선택할 수 있습니다. 사용 하는 **보안** 페이지에서 **ProjectDesigner** 응용 프로그램에 적합 한 영역을 요청 하려면. 또한 최종 사용자 환경을 에뮬레이트할 수 있는 제한 된 권한으로 응용 프로그램을 디버깅할 수 있습니다. 자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md).  
  
### <a name="clickonce-trust-prompt"></a>ClickOnce 신뢰 프롬프트  
 해당 영역에서 허용 된 것 보다 많은 사용 권한을 요청 하는 응용 프로그램 신뢰 결정을 내리는 데 최종 사용자 수 묻는. 최종 사용자는 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, 콘솔 응용 프로그램, XAML 브라우저 응용 프로그램 및 Office 솔루션의 ClickOnce 응용 프로그램 실행 되도록 신뢰 되었는지 결정할 수 있습니다. 자세한 내용은 [하는 방법: ClickOnce 신뢰 프롬프트 동작 구성](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).  
  
## <a name="how-clickonce-deployment-works"></a>ClickOnce 배포의 작동 방법  
 코어 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 아키텍처는 두 개의 XML 매니페스트 파일인 기반: 응용 프로그램 매니페스트 및 배포 매니페스트. 파일에서 ClickOnce 응용 프로그램의 설치 위치, 업데이트 방식 및 업데이트에 대해 설명 하는 데 사용 됩니다.  
  
### <a name="publishing-clickonce-applications"></a>ClickOnce 응용 프로그램 게시  
 응용 프로그램 매니페스트는 응용 프로그램 자체에 대해 설명합니다. 어셈블리 종속성과 응용 프로그램, 필수 권한 및 업데이트 사용할 수 있습니다 위치를 구성 하는 파일이 포함 됩니다. 응용 프로그램 개발자는 응용 프로그램 매니페스트의 게시 마법사에서 Visual Studio 매니페스트 생성 및 편집 도구 (Mage.exe)를 사용 하 여 작성자에 게는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
 배포 매니페스트는 응용 프로그램을 배포 하는 방법을 설명 합니다. 응용 프로그램 매니페스트의 위치 및 클라이언트가 실행할 응용 프로그램 버전이 포함 됩니다.  
  
### <a name="deploying-clickonce-applications"></a>ClickOnce 응용 프로그램 배포  
 를 만든 후 배포 매니페스트는 배포 위치에 복사 됩니다. 웹 서버, 네트워크 파일 공유 또는 CD와 같은 미디어 수 있습니다. 응용 프로그램 매니페스트와 모든 응용 프로그램 파일 배포 매니페스트에 지정 된 배포 위치에 복사 됩니다. 이 배포 위치와 동일 하거나 다른 위치를 수 있습니다. 사용 하는 경우는 **게시 마법사** Visual Studio 복사 작업이 자동으로 수행 됩니다.  
  
### <a name="installing-clickonce-applications"></a>ClickOnce 응용 프로그램 설치  
 배포 위치에 배포 된 후 최종 사용자가 다운로드 하 고 배포 매니페스트 파일 또는 폴더를 웹 페이지에 나타내는 아이콘을 클릭 하 여 응용 프로그램을 설치할 수 있습니다. 대부분의 경우에서 최종 사용자는 설치가 진행 되 고 추가 작업 없이 시작 될 응용 프로그램 설치를 확인 하 라는 간단한 대화 상자가 표시 됩니다. 승격 된 권한 또는 응용 프로그램은 신뢰할 수 있는 인증서로 서명 되지 않은 경우 응용 프로그램에 필요한 경우에도 대화 상자는 설치를 계속 하려면 사용 권한을 부여 하려면 사용자에 게 요청 합니다. ClickOnce 설치 사용자 당 인 경우에 관리자 권한이 필요한 필수 구성 요소가 있는 경우에 권한 상승 필요할 수 있습니다. 승격 된 사용 권한에 대 한 자세한 내용은 참조 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)합니다.  
  
 인증서 수 신뢰할 수 있는 컴퓨터 또는 엔터프라이즈 수준에서 신뢰할 수 있는 인증서로 서명 된 ClickOnce 응용 프로그램을 자동으로 설치할 수 있도록 합니다. 신뢰할 수 있는 인증서에 대 한 자세한 내용은 참조 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)합니다.  
  
 사용자의 응용 프로그램을 추가할 수 있습니다 **시작** 메뉴와는 **프로그램 추가 / 제거** 그룹에 **제어판**합니다. 다른 배포 기술을 달리 아무 것도 추가 된 **Program Files** 폴더 또는 레지스트리 및 관리 권한이 없는 설치에 필요한을  
  
> [!NOTE]
>  응용 프로그램에 추가 되지 않도록 방지할 수 이기도 **시작** 메뉴 및 **프로그램 추가 / 제거** 웹 응용 프로그램 처럼 동작 하도록 만들 그룹입니다. 자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하세요.  
  
### <a name="updating-clickonce-applications"></a>ClickOnce 응용 프로그램 업데이트  
 응용 프로그램 개발자가 응용 프로그램의 업데이트 된 버전을 만들 때 새 응용 프로그램 매니페스트를 생성 하며 파일 배포 위치에 복사-만들어서 원래 응용 프로그램 배포 폴더에 있습니다. 관리자는 응용 프로그램의 새 버전의 위치를 가리키도록 배포 매니페스트를 업데이트 합니다.  
  
> [!NOTE]
>  **게시 마법사** 이러한 단계를 수행 하려면 Visual Studio에서 사용할 수 있습니다.  
  
 배포 위치 외에도 배포 매니페스트는 응용 프로그램에서 업데이트 된 버전을 여기서 확인 한 업데이트 위치 (웹 페이지 또는 네트워크 파일 공유)도 포함 됩니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]**게시** 속성은 응용 프로그램 업데이트를 확인 하는 시기와 빈도 지정 하는 데 사용 됩니다. 배포 매니페스트의 업데이트 동작을 지정할 수 있습니다 또는 방법으로 응용 프로그램의 사용자 인터페이스에서 사용자 선택으로 제공할 수 있습니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Api입니다. 또한 **게시** 속성을 사용 하 업데이트를 필수로 또는 이전 버전으로 롤백할 수 있습니다. 자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md).  
  
### <a name="third-party-installers"></a>타사 설치 관리자  
 응용 프로그램과 함께 타사 구성 요소를 설치 하 여 ClickOnce 설치 관리자를 사용자 지정할 수 있습니다. 재배포 가능 패키지 (.exe 또는.msi 파일)를 포함 하며 언어 중립적인 제품 매니페스트 및 언어별로 패키지 매니페스트를 사용 하 여 패키지에 설명 합니다. 자세한 내용은 참조 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)합니다.  
  
## <a name="clickonce-tools"></a>ClickOnce 도구  
 다음 표에서 생성, 편집, 서명 하 고, 응용 프로그램 및 배포 매니페스트 다시 서명 하는 데 사용할 수 있는 도구를 보여 줍니다.  
  
|도구|설명|  
|----------|-----------------|  
|[프로젝트 디자이너, 보안 페이지](../ide/reference/security-page-project-designer.md)|응용 프로그램 및 배포 매니페스트를 등록 합니다.|  
|[프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)|생성 하 고 Visual Basic 및 Visual C# 응용 프로그램에 대 한 응용 프로그램 및 배포 매니페스트를 편집 합니다.|  
|[Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)|Visual Basic, Visual C# 및 Visual c + + 응용 프로그램에 대 한 응용 프로그램 및 배포 매니페스트를 생성합니다.<br /><br /> 서명 하 고 응용 프로그램 및 배포 매니페스트에 다시 서명 합니다.<br /><br /> 일괄 처리 스크립트 및 명령 프롬프트에서 실행할 수 있습니다.|  
|[MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)|생성 하 고 응용 프로그램 및 배포 매니페스트를 편집 합니다.<br /><br /> 서명 하 고 응용 프로그램 및 배포 매니페스트에 다시 서명 합니다.|  
|[GenerateApplicationManifest 작업](../msbuild/generateapplicationmanifest-task.md)|응용 프로그램 매니페스트를 생성합니다.<br /><br /> MSBuild에서 실행할 수 있습니다. 자세한 내용은 참조 [MSBuild 참조](../msbuild/msbuild-reference.md)합니다.|  
|[GenerateDeploymentManifest 작업](../msbuild/generatedeploymentmanifest-task.md)|배포 매니페스트를 생성합니다.<br /><br /> MSBuild에서 실행할 수 있습니다. 자세한 내용은 참조 [MSBuild 참조](../msbuild/msbuild-reference.md)합니다.|  
|[SignFile 작업](../msbuild/signfile-task.md)|응용 프로그램 및 배포 매니페스트를 등록 합니다.<br /><br /> MSBuild에서 실행할 수 있습니다. 자세한 내용은 참조 [MSBuild 참조](../msbuild/msbuild-reference.md)합니다.|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|응용 프로그램 및 배포 매니페스트를 생성 하려면 사용자 고유의 응용 프로그램을 개발 합니다.|  
  
 다음 표에서 다음이 브라우저에서 ClickOnce 응용 프로그램을 지 원하는 데 필요한.NET Framework 버전을 나타냅니다.  
  
|브라우저|.NET Framework 버전|  
|-------------|----------------------------|  
|Internet Explorer|2.0, 3.0, 3.5, 4, 3.5 SP1|  
|Firefox|2.0 S P 1에서는 3.5 S P 1에서는 4|  
  
## <a name="see-also"></a>참고 항목  
 [Windows Vista의 ClickOnce 배포](../deployment/clickonce-deployment-on-windows-vista.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce를 사용하여 COM 구성 요소 배포](../deployment/deploying-com-components-with-clickonce.md)   
 [명령줄에서 ClickOnce 응용 프로그램 빌드](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버그](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)