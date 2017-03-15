---
title: "ClickOnce 보안 및 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포"
  - "응용 프로그램 배포[ClickOnce]"
  - "게시, ClickOnce"
  - "Windows 응용 프로그램, ClickOnce 배포"
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
caps.latest.revision: 32
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 보안 및 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 최소한의 사용자 상호 작용으로 설치 및 실행할 수 있는 Windows 기반 자동 업데이트 응용 프로그램을 만들 수 있게 하는 배포 기술입니다. Visual Basic 및 Visual C\#으로 프로젝트를 개발하여 ClickOnce 기술로 응용 프로그램을 배포한 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 배포된 응용 프로그램의 게시 및 업데이트를 완벽하게 지원합니다.  Visual C\+\+ 응용 프로그램 배포에 대한 자세한 내용은 [Visual C\+\+ 응용 프로그램의 ClickOnce 배포](/visual-cpp/ide/clickonce-deployment-for-visual-cpp-applications)를 참조하십시오.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포는 배포와 관련된 세 가지 주요 문제를 해결합니다.  
  
-   **응용 프로그램 업데이트의 어려움.** Microsoft Windows Installer 배포에서는 응용 프로그램이 업데이트될 때마다 사용자가 업데이트인 msp 파일을 설치하고 이를 설치된 제품에 적용할 수 있습니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포에서는 업데이트를 자동으로 제공할 수 있습니다.  응용 프로그램에서 변경된 부분만 다운로드된 다음 새 side\-by\-side 폴더에서 업데이트된 전체 응용 프로그램이 다시 설치됩니다.  
  
-   **사용자 컴퓨터에 대한 영향.** Windows Installer 배포의 경우 응용 프로그램은 많은 경우 공유 구성 요소에 의존하지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 경우 각 응용 프로그램은 독립적이며 다른 응용 프로그램과 충돌할 수 없습니다.  
  
-   **보안 권한.** Windows Installer 배포의 경우 관리 권한이 필요하고 제한된 사용자 설치만 허용되지만, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 경우 관리 권한이 없는 사용자가 설치하고 응용 프로그램에 필요한 코드 액세스 보안 권한만 부여할 수 있습니다.  
  
 과거 이러한 문제로 인해 개발자는 쉽게 설치하기 위해 풍부한 인터페이스를 포기하면서 Windows 기반 응용 프로그램 대신 웹 응용 프로그램을 만들어야 했습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 배포한 응용 프로그램에서는 두 기술을 모두 가장 적합하게 사용할 수 있습니다.  
  
## ClickOnce 응용 프로그램의 정의  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기술을 사용하여 게시하는 Windows Presentation Foundation\(.xbap\), Windows Forms\(.exe\), 콘솔 응용 프로그램\(.exe\) 또는 Office 솔루션\(.dll\)입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 웹 페이지, 네트워크 파일 공유 또는 CD\-ROM과 같은 미디어를 통해 게시할 수 있습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 최종 사용자의 컴퓨터에 설치하거나 컴퓨터가 오프라인일 경우에도 로컬로 실행할 수 있고 최종 사용자의 컴퓨터에 영구적으로 설치하지 않고 온라인 전용 모드로 실행할 수도 있습니다.  자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하십시오.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 자동으로 업데이트할 수 있으며, 사용할 수 있는 최신 버전을 확인하여 자동으로 업데이트된 파일로 대체합니다.  개발자는 업데이트 동작을 지정할 수 있으며, 네트워크 관리자가 업데이트를 필수로 표시하는 등의 업데이트 전략을 제어할 수도 있습니다.  최종 사용자나 관리자가 업데이트를 이전 버전으로 롤백할 수도 있습니다.  자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)을 참조하십시오.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 격리되므로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치하거나 실행해도 기존 응용 프로그램을 중단할 수 없습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 독립적이며, 각 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 안전한 사용자별 및 응용 프로그램별 캐시에 설치되고 해당 캐시에서 실행됩니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 인터넷이나 인트라넷 보안 영역에서 실행됩니다.  필요한 경우 응용 프로그램에서는 고급 보안 권한을 요청할 수 있습니다.  자세한 내용은 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)을 참조하십시오.  
  
## ClickOnce 보안 작동 방식  
 핵심 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 보안은 인증서, 코드 액세스 보안 정책 및 ClickOnce 신뢰 프롬프트를 기반으로 합니다.  
  
### 인증서  
 Authenticode 인증서는 응용 프로그램 게시자의 신뢰성을 확인하는 데 사용됩니다.  응용 프로그램 배포에 Authenticode를 사용할 경우 ClickOnce는 신뢰할 수 있는 확인된 소스에서 가져온 올바른 프로그램으로 위장하려는 유해한 프로그램을 방지하는 데 도움이 됩니다.  필요에 따라서는 응용 프로그램 및 배포 매니페스트에 서명하여 해당 파일이 변조되지 않았음을 입증하기 위해 인증서를 사용할 수도 있습니다.  자세한 내용은 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)를 참조하십시오.  또한 인증서는 신뢰할 수 있는 게시자 목록을 보유하도록 클라이언트 컴퓨터를 구성하는 데 사용될 수 있습니다.  응용 프로그램을 신뢰할 수 있는 게시자에서 가져온 경우 사용자 상호 작용 없이 응용 프로그램을 설치할 수 있습니다.  자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)를 참조하십시오.  
  
### 코드 액세스 보안  
 코드 액세스 보안을 통해 보호된 리소스에 대한 코드의 액세스를 제한할 수 있습니다.  대부분의 경우 인터넷 또는 로컬 인트라넷 영역을 선택하여 사용 권한을 제한할 수 있습니다.  응용 프로그램에 적합한 영역을 요청하려면 **프로젝트 디자이너**의 **보안** 페이지를 사용합니다.  또한 제한된 사용 권한으로 응용 프로그램을 디버깅하여 최종 사용자 환경을 에뮬레이트할 수 있습니다.  자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)을 참조하십시오.  
  
### ClickOnce 신뢰 프롬프트  
 영역에서 허용하는 사용 권한보다 많은 사용 권한이 응용 프로그램에 필요한 경우 신뢰 여부를 결정하라는 메시지가 최종 사용자에게 표시될 수 있습니다.  최종 사용자는 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, 콘솔 응용 프로그램, XAML 브라우저 응용 프로그램 같은 ClickOnce 응용 프로그램을 신뢰하여 실행할지 여부를 결정할 수 있습니다.  자세한 내용은 [방법: ClickOnce 신뢰 프롬프트 동작 구성](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)을 참조하십시오.  
  
## ClickOnce 배포 작동 방식  
 핵심 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 아키텍처는 두 개의 XML 매니페스트 파일인 응용 프로그램 매니페스트 및 배포 매니페스트를 기반으로 합니다.  이러한 파일은 ClickOnce 응용 프로그램의 설치 위치, 업데이트 방식 및 업데이트 시점을 기술하는 데 사용됩니다.  
  
### ClickOnce 응용 프로그램 게시  
 응용 프로그램 매니페스트는 응용 프로그램 자체에 대해 설명합니다.  여기에는 어셈블리, 응용 프로그램을 구성하는 종속성과 파일, 필수 권한, 업데이트를 사용할 수 있는 위치 등이 포함됩니다.  응용 프로그램 개발자는 Visual Studio의 게시 마법사 또는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]의 매니페스트 생성 및 편집 도구\(Mage.exe\)를 사용하여 응용 프로그램 매니페스트를 작성합니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)를 참조하십시오.  
  
 배포 매니페스트는 응용 프로그램 배포 방법에 대해 설명합니다.  여기에는 응용 프로그램 매니페스트의 위치 및 클라이언트에서 실행해야 하는 응용 프로그램 버전이 포함됩니다.  
  
### ClickOnce 응용 프로그램 배포  
 만들어진 후 배포 매니페스트는 배포 위치에 복사됩니다.  배포 위치는 웹 서버, 네트워크 파일 공유 또는 CD와 같은 미디어가 될 수 있습니다.  응용 프로그램 매니페스트와 모든 응용 프로그램 파일도 배포 매니페스트에 지정된 배포 위치에 복사됩니다.  이 위치는 배포 위치와 같을 수도 있고 다를 수도 있습니다.  Visual Studio의 **게시 마법사**를 사용하면 복사 작업이 자동으로 수행됩니다.  
  
### ClickOnce 응용 프로그램 설치  
 매니페스트를 배포 위치에 배포한 후 최종 사용자는 웹 페이지나 폴더에서 배포 매니페스트 파일을 나타내는 아이콘을 클릭하여 응용 프로그램을 다운로드하고 설치할 수 있습니다.  대부분의 경우 최종 사용자에게는 설치 확인 여부를 묻는 단순한 대화 상자가 표시된 후 설치가 진행되고 응용 프로그램은 추가 개입 없이 시작됩니다.  또한 응용 프로그램에 고급 권한이 필요하거나 신뢰할 수 있는 인증서로 응용 프로그램이 서명되지 않은 경우 이 대화 상자에서는 설치를 진행하기 전에 사용자에게 권한을 부여할지 여부를 묻습니다.  ClickOnce 설치가 사용자별로 수행되기는 하지만 관리자 권한이 필요한 필수 구성 요소가 있는 경우에는 권한 높이기가 요청될 수 있습니다.  고급 권한에 대한 자세한 내용은 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)을 참조하십시오.  
  
 신뢰할 수 있는 인증서로 서명된 ClickOnce 응용 프로그램이 자동으로 설치될 수 있도록 컴퓨터 또는 기업 수준에서 인증서를 신뢰할 수 있습니다.  신뢰할 수 있는 인증서에 대한 자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)를 참조하십시오.  
  
 응용 프로그램이 **시작** 메뉴 및 **제어판**의 **프로그램 추가\/제거** 그룹에 추가될 수 있습니다.  다른 배포 기술과 달리 **Program Files** 폴더 또는 레지스트리에는 아무 것도 추가되지 않으며 설치하는 데 관리자 권한이 필요합니다.  
  
> [!NOTE]
>  또한 응용 프로그램이 **시작** 메뉴 및 **프로그램 추가\/제거** 그룹에 추가되지 않도록 하여 응용 프로그램이 웹 응용 프로그램처럼 동작하도록 만들 수 있습니다.  자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하십시오.  
  
### ClickOnce 응용 프로그램 업데이트  
 응용 프로그램 개발자가 업데이트된 버전의 응용 프로그램을 만들 경우 개발자는 새 응용 프로그램 매니페스트를 생성하고 파일을 배포 위치에 복사합니다. 배포 위치는 일반적으로 원래 응용 프로그램 배포 폴더의 형제 폴더입니다.  관리자는 배포 매니페스트를 업데이트하여 새 응용 프로그램 버전의 위치를 지정합니다.  
  
> [!NOTE]
>  Visual Studio의 **게시 마법사**를 사용하여 이러한 단계를 수행할 수 있습니다.  
  
 배포 매니페스트에서는 배포 위치 및 응용 프로그램이 업데이트된 버전을 확인하는 업데이트 위치\(웹 페이지 또는 네트워크 파일 공유\)가 들어 있습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] **게시** 속성을 사용하여 응용 프로그램이 업데이트를 확인하는 시기 및 빈도를 지정합니다.  업데이트 동작은 배포 매니페스트에서 지정하거나 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] API를 사용하여 응용 프로그램의 사용자 인터페이스에서 사용자 선택으로 제공할 수 있습니다.  또한 **게시** 속성을 사용하여 업데이트를 필수로 만들거나 이전 버전으로 롤백할 수 있습니다.  자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)을 참조하십시오.  
  
### 타사 설치 관리자  
 ClickOnce 설치 관리자를 사용자 지정하여 타사 구성 요소를 응용 프로그램과 함께 설치할 수 있습니다.  이렇게 하려면 재배포 가능 패키지\(.exe 또는 .msi 파일\)가 있어야 하며 언어 중립적인 제품 매니페스트 및 언어별 패키지 매니페스트로 패키지를 기술해야 합니다.  자세한 내용은 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)를 참조하십시오.  
  
## ClickOnce 도구  
 다음 표에서는 응용 프로그램 및 배포 매니페스트의 생성, 편집, 서명 및 재서명에 사용할 수 있는 도구를 보여 줍니다.  
  
|도구|설명|  
|--------|--------|  
|[프로젝트 디자이너, 보안 페이지](../ide/reference/security-page-project-designer.md)|응용 프로그램 및 배포 매니페스트에 서명합니다.|  
|[프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)|Visual Basic 및 Visual C\# 응용 프로그램에 필요한 응용 프로그램 및 배포 매니페스트를 생성하고 편집합니다.|  
|[Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)|Visual Basic, Visual C\# 및 Visual C\+\+ 응용 프로그램에 필요한 응용 프로그램 및 배포 매니페스트를 생성합니다.<br /><br /> 응용 프로그램 및 배포 매니페스트에 서명하고 다시 서명합니다.<br /><br /> 배치 스크립트 및 명령 프롬프트를 통해 실행할 수 있습니다.|  
|[MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)|응용 프로그램 및 배포 매니페스트를 생성하고 편집합니다.<br /><br /> 응용 프로그램 및 배포 매니페스트에 서명하고 다시 서명합니다.|  
|[GenerateApplicationManifest Task](../msbuild/generateapplicationmanifest-task.md)|응용 프로그램 매니페스트를 생성합니다.<br /><br /> MSBuild에서 실행될 수 있습니다.  자세한 내용은 [MSBuild Reference](../msbuild/msbuild-reference.md)를 참조하십시오.|  
|[GenerateDeploymentManifest Task](../msbuild/generatedeploymentmanifest-task.md)|배포 매니페스트를 생성합니다.<br /><br /> MSBuild에서 실행될 수 있습니다.  자세한 내용은 [MSBuild Reference](../msbuild/msbuild-reference.md)를 참조하십시오.|  
|[SignFile Task](../msbuild/signfile-task.md)|응용 프로그램 및 배포 매니페스트에 서명합니다.<br /><br /> MSBuild에서 실행될 수 있습니다.  자세한 내용은 [MSBuild Reference](../msbuild/msbuild-reference.md)를 참조하십시오.|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|사용자 고유 응용 프로그램을 개발하여 응용 프로그램 및 배포 매니페스트를 생성합니다.|  
  
 다음 표에서는 여러 브라우저에서 ClickOnce 응용 프로그램을 지원하는 데 필요한 .NET Framework 버전을 보여 줍니다.  
  
|브라우저|.NET Framework 버전|  
|----------|-----------------------|  
|Internet Explorer|2.0, 3.0, 3.5, 3.5 SP1, 4|  
|Firefox|2.0 SP1, 3.5 SP1, 4|  
  
## 참고 항목  
 [Windows Vista의 ClickOnce 배포](../deployment/clickonce-deployment-on-windows-vista.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce를 사용하여 COM 구성 요소 배포](../deployment/deploying-com-components-with-clickonce.md)   
 [명령줄에서 ClickOnce 응용 프로그램 빌드](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버깅](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)