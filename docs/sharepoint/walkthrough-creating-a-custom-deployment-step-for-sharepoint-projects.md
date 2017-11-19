---
title: "연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands
- SharePoint development in Visual Studio, extending deployment
ms.assetid: 4ba2d120-06b8-4ef3-84eb-c6c50ced9d82
caps.latest.revision: "63"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b7375071522ea59c9c00a5fa94277a3817438d25
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects"></a>연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기
  SharePoint 프로젝트를 배포 하면 Visual Studio는 일련의 배포 단계는 특정 순서로 실행 합니다. Visual Studio에는 많은 기본 제공 배포 단계가 포함 하지만 있습니다 수, 직접 만들 수도 있습니다.  
  
 이 연습에서는 SharePoint를 실행 하는 서버에서 솔루션 업그레이드 하는 사용자 지정 배포 단계에 만들어집니다. Visual Studio는 다양 한 작업, 이러한 제거 또는 추가 위한 솔루션을 기본 제공 배포 단계가 포함 되지만 솔루션 업그레이드에 대 한 배포 단계를 포함 하지 않습니다. 기본적으로 SharePoint 솔루션을 배포할 때 Visual Studio 먼저 취소 솔루션 (이미 배포 된) 경우 다음 전체 솔루션을 재배포 하 고 있습니다. 기본 제공 배포 단계에 대 한 자세한 내용은 참조 [배포, 게시 및 SharePoint 솔루션 패키지 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Visual Studio 확장을 만드는 두 가지 기본 작업을 수행 합니다.  
  
    -   SharePoint 솔루션을 업그레이드 하는 사용자 지정 배포 단계를 정의 하는 확장 합니다.  
  
    -   확장 일련의 지정된 된 프로젝트에 대해 실행 되는 배포 단계는 새 배포 구성을 정의 하는 프로젝트 확장을 만듭니다. 새 배포 구성에는 사용자 지정 배포 단계 및 몇 가지 기본 제공 배포 단계가 포함 됩니다.  
  
-   확장 프로그램 어셈블리를 호출 하는 두 개의 사용자 지정 SharePoint 명령 만들기 SharePoint 명령에는 Api를 사용 하는 서버 개체 모델에서 SharePoint에 대 한 확장 프로그램 어셈블리를 호출할 수 있는 메서드입니다. 자세한 내용은 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
-   확장 VSIX (Visual Studio)을 배포할 패키지를 두 어셈블리가 모두를 작성 합니다.  
  
-   새 배포 단계를 테스트 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 Windows, SharePoint 및 Visual Studio의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio SDK입니다. 이 연습에서는 **VSIX 프로젝트** VSIX 패키지 확장 배포를 만들려는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   서버 개체 모델을 사용 하 여 SharePoint에 대 한 합니다. 자세한 내용은 참조 [SharePoint Foundation 서버 측 개체 모델을 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=177796)합니다.  
  
-   SharePoint 솔루션입니다. 자세한 내용은 참조 [솔루션 개요](http://go.microsoft.com/fwlink/?LinkId=169422)합니다.  
  
-   SharePoint 솔루션을 업그레이드 합니다. 자세한 내용은 참조 [솔루션 업그레이드](http://go.microsoft.com/fwlink/?LinkId=177802)합니다.  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 세 개의 프로젝트를 만들어야 합니다.  
  
-   확장 배포 하려면 VSIX 패키지를 만들려면 VSIX 프로젝트.  
  
-   확장을 구현 하는 클래스 라이브러리 프로젝트. 이 프로젝트는.NET Framework 4.5를 대상으로 해야 합니다.  
  
-   사용자 지정 SharePoint 명령을 정의 하는 클래스 라이브러리 프로젝트. 이 프로젝트는.NET Framework 3.5를 대상 해야 합니다.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드를 Visual Studio SDK를 설치 하는 경우에 사용할 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 필수 구성 요소 섹션을 참조 하십시오.  
  
4.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
5.  선택 된 **VSIX 프로젝트** 서식 파일을 프로젝트 이름 **UpgradeDeploymentStep**, 선택한 후는 **확인** 단추 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **UpgradeDeploymentStep** 프로젝트를 **솔루션 탐색기**합니다.  
  
#### <a name="to-create-the-extension-project"></a>확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**UpgradeDeploymentStep 솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **Windows** 노드.  
  
3.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
4.  선택 된 **클래스 라이브러리** 서식 파일 프로젝트에서 프로젝트 이름을 **DeploymentStepExtension**, 선택한 후는 **확인** 단추 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **DeploymentStepExtension** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
#### <a name="to-create-the-sharepoint-command-project"></a>SharePoint 명령 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**UpgradeDeploymentStep 솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **Windows** 노드.  
  
3.  선택 대화 상자 맨 위에 있는 **.NET Framework 3.5** 버전의.NET Framework의 목록에 있습니다.  
  
4.  선택 된 **클래스 라이브러리** 서식 파일 프로젝트에서 프로젝트 이름을 **SharePointCommands**, 선택한 후는 **확인** 단추 합니다.  
  
     Visual Studio 추가 **SharePointCommands** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-projects"></a>프로젝트 구성  
 사용자 지정 배포 단계를 만드는 코드를 작성 하기 전에 코드 파일 및 어셈블리 참조를 추가 해야 하며 프로젝트를 구성 해야 합니다.  
  
#### <a name="to-configure-the-deploymentstepextension-project"></a>DeploymentStepExtension 프로젝트를 구성 하려면  
  
1.  에 **DeploymentStepExtension** 프로젝트에서 다음과 같은 이름의 두 코드 파일을 추가 합니다.  
  
    -   UpgradeStep  
  
    -   DeploymentConfigurationExtension  
  
2.  DeploymentStepExtension 프로젝트의 바로 가기 메뉴를 열고 **참조 추가**합니다.  
  
3.  에 **프레임 워크** 탭에서 System.ComponentModel.Composition 어셈블리에 대 한 확인란을 선택 합니다.  
  
4.  에 **확장** 탭 Microsoft.VisualStudio.SharePoint 어셈블리에 대 한 확인란을 선택 하 고 선택 합니다는 **확인** 단추입니다.  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>SharePointCommands 프로젝트를 구성 하려면  
  
1.  에 **SharePointCommands** 프로젝트에서 명령을 라는 코드 파일을 추가 합니다.  
  
2.  **솔루션 탐색기**에서 바로 가기 메뉴를 열고는 **SharePointCommands** 프로젝트 노드를 선택한 후 **참조 추가**합니다.  
  
3.  에 **확장** 탭, 다음 어셈블리에 대 한 확인란을 선택 합니다. 선택한 다음 클릭은 **확인** 단추  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
## <a name="defining-the-custom-deployment-step"></a>사용자 지정 배포 단계를 정의합니다.  
 업그레이드 배포 단계를 정의 하는 클래스를 만듭니다. 클래스 구현 배포 단계를 정의 하는 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> 인터페이스입니다. 사용자 지정 배포 단계를 정의 하려는 경우이 인터페이스를 구현 합니다.  
  
#### <a name="to-define-the-custom-deployment-step"></a>사용자 지정 배포 단계를 정의 하려면  
  
1.  에 **DeploymentStepExtension** 프로젝트 UpgradeStep 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
    > [!NOTE]  
    >  이 코드를 추가, 프로젝트를 컴파일 오류 일부 있지만 자리를 비울 갈 후 추가 하면 코드 이후 단계에서.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/upgradestep.cs#1)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/upgradestep.vb#1)]  
  
## <a name="creating-a-deployment-configuration-that-includes-the-custom-deployment-step"></a>사용자 지정 배포 단계를 포함 하는 배포 구성 만들기  
 여러 기본 제공 배포 단계 및 새 업그레이드 배포 단계를 포함 하는 새 배포 구성에 대 한 프로젝트 확장을 만듭니다. 이 확장 프로그램을 만들면 SharePoint 개발자가 SharePoint 프로젝트의 업그레이드 배포 단계를 사용 하도록 도울 수 있습니다.  
  
 클래스 구현 배포 구성을 만드는 데는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스입니다. SharePoint 프로젝트 확장을 만들려는 경우에이 인터페이스를 구현 합니다.  
  
#### <a name="to-create-the-deployment-configuration"></a>배포 구성을 만들려면  
  
1.  
  
2.  에 **DeploymentStepExtension** 프로젝트 DeploymentConfigurationExtension 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/deploymentconfigurationextension.cs#2)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/deploymentconfigurationextension.vb#2)]  
  
## <a name="creating-the-custom-sharepoint-commands"></a>사용자 지정 SharePoint 명령 만들기  
 SharePoint에 대 한 서버 개체 모델을 호출 하는 두 개의 사용자 지정 명령을 만듭니다. 하나의 명령 여부는 솔루션을 이미 배포한; 결정 다른 명령을 솔루션을 업그레이드합니다.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint 명령을 정의 하려면  
  
1.  에 **SharePointCommands** 프로젝트 명령 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/SharePointCommands/Commands.cs#4)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/sharepointcommands/commands.vb#4)]  
  
## <a name="checkpoint"></a>검사점  
 이 연습에서는 사용자 지정 배포 단계 및 SharePoint 명령에 대 한 모든 코드 프로젝트에 포함 됩니다. 오류 없이 컴파일됩니다 있는지 확인 하도록 빌드하십시오.  
  
#### <a name="to-build-the-projects"></a>프로젝트를 빌드  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **DeploymentStepExtension** 프로젝트를 선택한 후 **빌드**합니다.  
  
2.  에 대 한 바로 가기 메뉴를 열고는 **SharePointCommands** 프로젝트를 선택한 후 **빌드**합니다.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>확장 배포 하려면 VSIX 패키지 만들기  
 확장을 배포 하려면 솔루션에서 VSIX 프로젝트를 사용 하 여 VSIX 패키지를 만듭니다. 첫째, VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다. 그런 다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>구성 하 고 VSIX 패키지를 만들려면  
  
1.  **솔루션 탐색기**아래는 **UpgradeDeploymentStep** 프로젝트에 대 한 바로 가기 메뉴를 열고는 **source.extension.vsixmanifest** 파일을 선택한 다음 선택 **열기**합니다.  
  
     Visual Studio 매니페스트 편집기에서 파일을 엽니다. Source.extension.vsixmanifest 파일은 필요한 모든 VSIX 패키지 extension.vsixmanifest 파일의 기준이 됩니다. 이 파일에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다.  
  
2.  에 **제품 이름** 상자에 입력 **SharePoint 프로젝트에 대 한 배포 단계 업그레이드**합니다.  
  
3.  에 **작성자** 상자에 입력 **Contoso**합니다.  
  
4.  에 **설명** 상자에 입력 **SharePoint 프로젝트에 사용할 수 있는 사용자 지정 업그레이드 배포 단계 제공**합니다.  
  
5.  에 **자산** 탭 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
6.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `MefComponent` extension.vsixmanifest 파일의 요소입니다. 이 요소는 VSIX 패키지의 확장 어셈블리의 이름을 지정합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
7.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
8.  에 **프로젝트** 목록에서 선택 **DeploymentStepExtension**를 선택한 후는 **확인** 단추입니다.  
  
9. 매니페스트 편집기에서 선택 된 **새로** 단추를 다시 합니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
10. 에 **형식** 목록에서 입력 **SharePoint.Commands.v4**합니다.  
  
    > [!NOTE]  
    >  이 요소는 Visual Studio 확장에 포함 하려는 사용자 지정 확장을 지정 합니다. 자세한 내용은 참조 [자산 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737)합니다.  
  
11. 에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
12. 에 **프로젝트** 목록에서 선택 **SharePointCommands**를 선택한 후는 **확인** 단추입니다.  
  
13. 메뉴 모음에서 **빌드**, **솔루션 빌드**, 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
14. UpgradeDeploymentStep 프로젝트에 대 한 빌드 출력 폴더 UpgradeDeploymentStep.vsix 파일을 이제 포함 되어 있는지 확인 합니다.  
  
     빌드 출력 폴더는 기본적으로는... 프로젝트 파일에 포함 된 폴더 아래 \bin\Debug 폴더입니다.  
  
## <a name="preparing-to-test-the-upgrade-deployment-step"></a>업그레이드 배포 단계를 테스트 하기 위해 준비  
 업그레이드 배포 단계를 테스트 하려면 먼저 SharePoint 사이트에 샘플 솔루션을 배포 해야 합니다. Visual Studio의 실험적 인스턴스에서 확장을 디버그 하 여 시작 합니다. 목록 정의와 목록 인스턴스 배포 단계를 테스트 하는 데 만들고 SharePoint 사이트에 배포 합니다. 다음에 목록 정의와 목록 인스턴스를 수정 하 고 다시를 배포 하는 기본 배포 프로세스 솔루션 SharePoint 사이트에서를 덮어씁니다 방법을 보여 줍니다.  
  
 이 연습의 뒷부분에서 수정 하면서 간단한 목록 정의와 목록 인스턴스 및 있습니다 수에서 업그레이드 하는 SharePoint 사이트.  
  
#### <a name="to-start-debugging-the-extension"></a>확장 프로그램 디버깅을 시작 하려면  
  
1.  관리 자격 증명으로 Visual Studio를 다시 시작 하 고 UpgradeDeploymentStep 솔루션을 엽니다.  
  
2.  DeploymentStepExtension 프로젝트에서 UpgradeStep 코드 파일을 열고 다음 코드의 첫 번째 줄에 중단점을 추가 `CanExecute` 및 `Execute` 메서드.  
  
3.  F5 키를 선택 하 여 하거나 메뉴 모음에서 디버깅, 선택 시작 **디버그**, **디버깅 시작**합니다.  
  
4.  Visual Studio SharePoint Projects\1.0에 대 한 배포 단계 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Upgrade에 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에서 업그레이드 배포 단계를 테스트 합니다.  
  
#### <a name="to-create-a-sharepoint-project-with-a-list-definition-and-a-list-instance"></a>목록 정의와 목록 인스턴스를 사용 하 여 SharePoint 프로젝트를 만들려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **파일**, **새로**, **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 노드 또는 **Visual Basic** 노드를 확장 하 고는 **SharePoint** 노드를 선택한 후 **2010** 노드.  
  
3.  대화 상자 위쪽에 있는지 확인 하는 **.NET Framework 3.5** 버전의.NET Framework의 목록에 나타납니다.  
  
     에 대 한 프로젝트 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 이 버전의.NET Framework가 필요 합니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **SharePoint 2010 프로젝트**, 프로젝트 이름을 **EmployeesListDefinition**를 선택한 후는 **확인** 단추입니다.  
  
5.  에 **SharePoint 사용자 지정 마법사**, 디버깅을 위해 사용 하려는 사이트의 URL을 입력 합니다.  
  
6.  아래 **이 SharePoint 솔루션에 대 한 신뢰 수준을**, 선택는 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
    > [!NOTE]  
    >  업그레이드 배포 단계는 샌드 박싱된 솔루션을 지원 하지 않습니다.  
  
7.  선택 된 **마침** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]EmployeesListDefinition 프로젝트를 만듭니다.  
  
8.  EmployeesListDefinition 프로젝트에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 항목**합니다.  
  
9. 에 **새 항목 추가-EmployeesListDefinition** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
10. 선택 된 **목록** 항목 템플릿, 항목 이름을 **직원 목록이**, 선택한 후는 **추가** 단추 합니다.  
  
     SharePoint 사용자 지정 마법사가 나타납니다.  
  
11. 에 **목록 설정 선택** 페이지에서 다음 설정을 확인 한 다음 선택에서 **마침** 단추:  
  
    1.  **직원 목록이** 에 표시는 **어떤 이름을 목록에 표시 하 시겠습니까?** 상자입니다.  
  
    2.  **기반으로 사용자 지정 가능한 목록을 만들:** 옵션 단추를 선택 합니다.  
  
    3.  **기본값 (비어 있음)** 에서 선택한는 **기반으로 사용자 지정 가능한 목록을 만들:** 목록입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]제목 열 및 하나의 빈 인스턴스로 직원 목록 항목을 만들고 목록 디자이너를 엽니다.  
  
12. 목록 디자이너에서에 **열** 탭을 선택는 **기존 또는 새 열 이름을 입력** 행을 한 후에 다음 열을 추가 **열 표시 이름** 목록:  
  
    1.  이름  
  
    2.  회사  
  
    3.  회사 전화  
  
    4.  전자 메일  
  
13. 모든 파일을 저장 한 다음 목록 디자이너를 닫습니다.  
  
14. **솔루션 탐색기**, 확장 하 고는 **직원 목록이** 노드를 차례로 확장 하 고는 **직원 목록 인스턴스** 자식 노드.  
  
15. Elements.xml 파일에서 기본 XML이이 파일에 다음 XML로 대체 합니다. 목록의 이름을 변경 하는이 XML **직원** Jim 중 배에 이름이 지정 하는 직원이 대 한 정보를 추가 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
        <Data>  
          <Rows>  
            <Row>  
              <Field Name="Title">Hance</Field>  
              <Field Name="FirstName">Jim</Field>  
              <Field Name="Company">Contoso</Field>  
              <Field Name="Business Phone">555-555-5555</Field>  
              <Field Name="E-Mail">jim@contoso.com</Field>  
            </Row>  
          </Rows>  
        </Data>  
      </ListInstance>  
    </Elements>  
    ```  
  
16. 저장 하 고 Elements.xml 파일을 닫습니다.  
  
17. EmployeesListDefinition 프로젝트에 대 한 바로 가기 메뉴를 연 다음 선택 **열려** 또는 **속성**합니다.  
  
     속성이 디자이너가 열립니다.  
  
18. 에 **SharePoint** 탭을 선택 취소 된 **디버깅 후 자동 취소** 확인란을 선택한 다음 속성을 저장 합니다.  
  
#### <a name="to-deploy-the-list-definition-and-list-instance"></a>목록 정의와 목록 인스턴스를 배포 하려면  
  
1.  **솔루션 탐색기**, 선택는 **EmployeesListDefinition** 프로젝트 노드.  
  
2.  에 **속성** 창 있는지 확인은 **활성 배포 구성** 속성이로 설정 되어 **기본**합니다.  
  
3.  F5 키를 선택 하거나 메뉴 모음에서 **디버그**, **디버깅 시작**합니다.  
  
4.  프로젝트가 성공적으로 빌드 되었는지, SharePoint 사이트에 웹 브라우저 열리는지 확인 하는 **나열** 빠른 실행 표시줄에서 항목에는 새 포함 됩니다. **직원** 하 고 목록에서  **직원** Jim 중 배에 대 한 항목 목록에 포함 됩니다.  
  
5.  웹 브라우저를 닫습니다.  
  
#### <a name="to-modify-the-list-definition-and-list-instance-and-redeploy-them"></a>목록 정의와 목록 인스턴스를 수정 하 고 다시 배포 하려면  
  
1.  EmployeesListDefinition 프로젝트를 열고의 자식인 Elements.xml 파일에서 **직원 목록 인스턴스** 프로젝트 항목입니다.  
  
2.  제거는 `Data` 요소와 그 자식 Jim 중 배에 대 한 목록에서 항목을 제거 하려면.  
  
     완료 하면 다음 XML 파일에 포함 되어야 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
      </ListInstance>  
    </Elements>  
    ```  
  
3.  저장 하 고 Elements.xml 파일을 닫습니다.  
  
4.  에 대 한 바로 가기 메뉴를 열고는 **직원 목록이** 프로젝트 항목을 선택한 후 **열려** 또는 **속성**합니다.  
  
5.  목록 디자이너에서 선택 된 **뷰** 탭 합니다.  
  
6.  에 **선택한 열** 목록에서 선택 **첨부 파일**, 선택한 후는 < 키 열을 이동 하는 **사용 가능한 열** 목록입니다.  
  
7.  이동 하려면 이전 단계를 반복 하는 **회사 전화** 열에서는 **선택한 열** 목록을 **사용 가능한 열** 목록입니다.  
  
     이 작업의 기본 보기에서 이러한 필드를 제거는 **직원** SharePoint 사이트의 목록입니다.  
  
8.  F5 키를 선택 하 여 하거나 메뉴 모음에서 디버깅, 선택 시작 **디버그**, **디버깅 시작**합니다.  
  
9. 확인 된 **배포 충돌** 대화 상자가 나타납니다.  
  
     이 대화 상자에 해당 솔루션이 이미 있는 배포 된 SharePoint 사이트에 Visual Studio 솔루션 (목록 인스턴스)를 배포 하려고 할 때 나타납니다. 이 연습 뒷부분 업그레이드 배포 단계를 실행할 때이 대화 상자 표시 되지 않습니다.  
  
10. 에 **배포 충돌** 대화 상자에서 선택 하는 **자동 해결** 옵션 단추입니다.  
  
     Visual Studio는 SharePoint 사이트에서 목록 인스턴스를 삭제 하 고 프로젝트에 목록 항목을 배포 후 SharePoint 사이트를 엽니다.  
  
11. 에 **나열** 섹션 빠른 실행 표시줄의 선택은 **직원** 목록으로 이동한 후 다음 정보를 확인 하십시오:  
  
    -   **첨부 파일** 및 **집 전화** 열 목록의이 뷰에 나타나지 않습니다.  
  
    -   목록이 비어 있습니다. 사용 하는 경우는 **기본** 솔루션을 다시 배포 하려면 배포 구성의 **직원** 목록이 프로젝트에서 새로운 빈 목록으로 바뀌었습니다.  
  
## <a name="testing-the-deployment-step"></a>테스트 배포 단계  
 이제 업그레이드 배포 단계를 테스트할 준비가 되었습니다. SharePoint에서 목록 인스턴스를 먼저 항목을 추가 합니다. 다음 목록 정의와 목록 인스턴스를 변경 하 고 SharePoint 사이트에서 업그레이드 하 업그레이드 배포 단계는 새 항목을 덮어쓰지 있는지 확인 합니다.  
  
#### <a name="to-manually-add-an-item-to-the-list"></a>목록에 항목을 수동으로 추가 하려면  
  
1.  SharePoint 사이트에서 리본 메뉴에 아래의 **목록 도구** 탭을 선택는 **항목** 탭 합니다.  
  
2.  에 **새로** 그룹에서 선택 **새 항목**합니다.  
  
     선택할 수 있습니다는 **새 항목 추가** 자체 항목 목록에 링크 합니다.  
  
3.  에 **직원-새 항목** 창에는 **제목** 상자에 입력 **시설을 운영 관리자**합니다.  
  
4.  에 **이름** 상자에 입력 **Andy**합니다.  
  
5.  에 **회사** 상자에서 입력 **Contoso**합니다.  
  
6.  선택 된 **저장** 단추, 목록에 새 항목이 표시 되는지 확인 한 다음 웹 브라우저를 닫습니다.  
  
     이 연습의 뒷부분에서 업그레이드 배포 단계가 목록의 콘텐츠를 덮어쓴다는 하지 않는 것을 확인 하려면이 항목을 사용 합니다.  
  
#### <a name="to-test-the-upgrade-deployment-step"></a>업그레이드 배포 단계를 테스트 하려면  
  
1.  Visual Studio의 실험적 인스턴스에서 **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **EmployeesListDefinition** 프로젝트 노드를 선택한 후 **속성**.  
  
     속성 편집기/디자이너가 열립니다.  
  
2.  에 **SharePoint** 탭에서 설정 된 **활성 배포 구성** 속성을 **업그레이드**합니다.  
  
     이 사용자 지정 배포 구성은 새 업그레이드 배포 단계를 포함합니다.  
  
3.  에 대 한 바로 가기 메뉴를 열고는 **직원 목록이** 프로젝트 항목을 선택한 후 **속성** 또는 **열려**합니다.  
  
     속성 편집기/디자이너가 열립니다.  
  
4.  에 **뷰** 탭을 선택는 **전자 메일** 열을 선택한 후는  **<**  해당 열을 이동 하는 키의 **열을선택한**목록을 **사용 가능한 열** 목록입니다.  
  
     이 작업의 기본 보기에서 이러한 필드를 제거는 **직원** SharePoint 사이트의 목록입니다.  
  
5.  F5 키를 선택 하 여 하거나 메뉴 모음에서 디버깅, 선택 시작 **디버그**, **디버깅 시작**합니다.  
  
6.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `CanExecute` 메서드.  
  
7.  F5 키를 다시 선택 하거나 메뉴 모음에서 **디버그**, **계속**합니다.  
  
8.  코드에서 이전에 설정한 중단점에서 중지 확인는 `Execute` 메서드.  
  
9. F5 키를 선택 하거나 메뉴 모음에서 **디버그**, **계속** 를 마지막으로 합니다.  
  
     웹 브라우저는 SharePoint 사이트를 엽니다.  
  
10. 에 **나열** 섹션의 빠른 실행 영역을 선택는 **직원** 목록으로 이동한 후 다음 세부 정보 확인:  
  
    -   이전 버전 (에 대 한 Andy, 시설을 운영 관리자)에 수동으로 추가 하는 항목 목록입니다.  
  
    -   **회사 전화** 및 **전자 메일 주소** 열 목록의이 뷰에 나타나지 않습니다.  
  
     **업그레이드** 기존 배포 구성 수정 **직원** SharePoint 사이트에서 목록 인스턴스. 사용 하는 경우는 **기본** 대신 배포 구성의 **업그레이드** 구성, 배포 충돌이 발생 합니다. Visual Studio는 대체 하 여 충돌을 해결는 **직원** 목록과 Andy, 시설을 운영 관리자에 대 한 항목 삭제 됩니다.  
  
## <a name="cleaning-up-the-development-computer"></a>개발 컴퓨터를 정리합니다.  
 테스트 업그레이드 배포 단계를 마친 후 SharePoint 사이트에서 목록 인스턴스 및 목록 정의 제거 하 고 Visual Studio에서 배포 단계 확장을 제거 합니다.  
  
#### <a name="to-remove-the-list-instance-from-the-sharepoint-site"></a>SharePoint 사이트에서 목록 인스턴스를 제거 하려면  
  
1.  열기는 **직원** 목록 아직 열리지 않은 경우 SharePoint 사이트에서 목록입니다.  
  
2.  SharePoint 사이트에 대 한 리본 메뉴에서 선택 된 **목록 도구** 탭을 선택한 후는 **목록** 탭 합니다.  
  
3.  에 **설정** 그룹에서 선택 된 **목록 설정** 항목입니다.  
  
4.  아래 **사용 권한 및 관리**, 선택는 **이 목록을 삭제** 명령에서 선택 **확인** 목록 휴지통에 보내고 웹 닫습니다를 것인지 브라우저.  
  
#### <a name="to-remove-the-list-definition-from-the-sharepoint-site"></a>SharePoint 사이트에서 목록 정의 제거 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **빌드**, **Retract**합니다.  
  
     Visual Studio는 SharePoint 사이트에서 목록 정의 제거 합니다.  
  
#### <a name="to-uninstall-the-extension"></a>확장을 제거하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택 **SharePoint 프로젝트에 대 한 배포 단계 업그레이드**, 선택한 후는 **제거** 명령입니다.  
  
3.  표시 되는 대화 상자에서 선택 **예** 확장을 제거 하 고 다음을 선택 하도록 확인할 수 **지금 다시 시작** 제거를 완료 합니다.  
  
4.  Visual Studio (실험적 인스턴스 및 UpgradeDeploymentStep 솔루션 열릴 Visual Studio의 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 패키징 및 배포 확장](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  