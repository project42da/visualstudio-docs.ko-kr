---
title: "Walkthrough: Creating a Custom Deployment Step for SharePoint Projects"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint commands"
  - "SharePoint development in Visual Studio, extending deployment"
ms.assetid: 4ba2d120-06b8-4ef3-84eb-c6c50ced9d82
caps.latest.revision: 63
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 62
---
# Walkthrough: Creating a Custom Deployment Step for SharePoint Projects
  SharePoint 프로젝트를 배포할 때 Visual Studio 일련의 배포 단계는 특정 순서로 실행 합니다.  Visual Studio에는 많은 기본 제공 배포 단계가 포함되어 있지만 사용자가 직접 만들 수도 있습니다.  
  
 이 연습에서는 Sharepoint를 실행 하는 서버에 솔루션을 업그레이드 하는 사용자 지정 배포 단계를 만듭니다.  Visual Studio 많은 작업, 그러한 축소 또는 솔루션을 추가 하는 기본 제공 배포 단계가 포함 되어 있지만 솔루션 업그레이드 배포 단계가 포함 되지 않습니다.  SharePoint 솔루션을 배포 하는 경우 \(이미 배포 된 경우\) 기본적으로 Visual Studio 먼저 솔루션 제거 하 고 전체 솔루션을 redeploys.  기본 배포 단계에 대한 자세한 내용은 [SharePoint 솔루션 패키지 배포, 게시 및 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)를 참조하십시오.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   다음 두 가지 주요 작업을 수행하는 Visual Studio 확장 만들기  
  
    -   확장 SharePoint 솔루션을 업그레이드 하는 사용자 지정 배포 단계를 정의 합니다.  
  
    -   확장 집합의 지정 된 프로젝트에 대해 실행 되는 배포 단계입니다 새 배포 구성을 정의 하는 프로젝트 확장을 만듭니다.  새 배포 구성에는 사용자 지정 배포 단계와 여러 개의 기본 제공 배포 단계가 포함됩니다.  
  
-   확장 어셈블리를 호출 하는 두 사용자 지정 SharePoint 명령을 만듭니다.  SharePoint 명령을 확장 어셈블리에 대 한 SharePoint 서버 개체 모델의 Api를 사용 하 여 호출할 수 있는 메서드입니다.  자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
-   두 어셈블리를 모두 배포하기 위한 VSIX\(Visual Studio Extension\) 패키지 빌드  
  
-   새 배포 단계 테스트  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전의 Windows, SharePoint 및 Visual Studio.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio SDK입니다.  이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 확장을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   Sharepoint에 대 한 서버 개체 모델을 사용 합니다.  자세한 내용은 [Using the SharePoint Foundation Server\-Side Object Model](http://go.microsoft.com/fwlink/?LinkId=177796)을 참조하십시오.  
  
-   SharePoint 솔루션.  자세한 내용은 [Solutions Overview](http://go.microsoft.com/fwlink/?LinkId=169422)를 참조하십시오.  
  
-   SharePoint 솔루션 업그레이드.  자세한 내용은 [Upgrading a Solution](http://go.microsoft.com/fwlink/?LinkId=177802)을 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료 하려면 세 프로젝트를 만들어야 합니다.  
  
-   VSIX 패키지를 만들어 확장을 배포하기 위한 VSIX 프로젝트  
  
-   확장을 구현하는 클래스 라이브러리 프로젝트.  .NET Framework 4.5이이 프로젝트를 대상으로 해야 합니다.  
  
-   사용자 지정 SharePoint 명령을 정의하는 클래스 라이브러리 프로젝트.  이 프로젝트.NET Framework 3.5 대상으로 지정 해야 합니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 또는  **Visual Basic** 노드를 다음 선택은  **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드인 Visual Studio SDK를 설치한 경우에 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
4.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
5.  선택은  **VSIX 프로젝트** 템플릿, 프로젝트 이름  **UpgradeDeploymentStep**, 다음 선택은  **확인** 단추.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **UpgradeDeploymentStep** 프로젝트를 추가합니다.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, UpgradeDeploymentStep 솔루션 노드에 대 한 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 또는  **Visual Basic** 노드를 다음 선택은  **Windows** 노드.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
4.  선택은  **클래스 라이브러리** : 프로젝트 이름, 프로젝트 템플릿  **DeploymentStepExtension**, 다음 선택은  **확인** 단추.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **DeploymentStepExtension** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
#### SharePoint 명령 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, UpgradeDeploymentStep 솔루션 노드에 대 한 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장  **C\#** 또는  **Visual Basic**, 다음 선택은  **Windows** 노드.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 3.5** .NET Framework 버전의 목록에서입니다.  
  
4.  선택은  **클래스 라이브러리** : 프로젝트 이름, 프로젝트 템플릿  **SharePointCommands**, 다음 선택은  **확인** 단추.  
  
     **SharePointCommands** 프로젝트가 솔루션에 추가되고 기본 Class1 코드 파일이 열립니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 프로젝트 구성  
 사용자 지정 배포 단계를 만드는 코드를 작성 하기 전에 코드 파일과 어셈블리 참조를 추가 해야 하 고 프로젝트를 구성 해야 합니다.  
  
#### DeploymentStepExtension 프로젝트를 구성하려면  
  
1.  에  **DeploymentStepExtension** 프로젝트에 다음과 같은 이름의 코드 파일 두 개를 추가 합니다.  
  
    -   UpgradeStep  
  
    -   DeploymentConfigurationExtension  
  
2.  DeploymentStepExtension 프로젝트 바로 가기 메뉴를 열고 선택  **참조 추가**.  
  
3.  에  **Framework** 탭에서 System.ComponentModel.Composition 어셈블리에 대 한 확인란을 선택 합니다.  
  
4.  에  **확장명** 탭 Microsoft.VisualStudio.SharePoint 어셈블리에 대 한 확인란을 선택 하 고 다음을 선택의  **확인** 단추.  
  
#### SharePointCommands 프로젝트를 구성하려면  
  
1.  에  **SharePointCommands** 프로젝트에 명령을 라는 코드 파일을 추가 합니다.  
  
2.  **솔루션 탐색기**, 바로 가기 메뉴에서 열기를  **SharePointCommands** 프로젝트 노드 및 다음 선택  **참조 추가**.  
  
3.  에  **확장명** 탭, 다음 어셈블리에 대 한 확인란을 선택 하 고 클릭을 선택의  **확인** 단추  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
## 사용자 지정 배포 단계 정의  
 업그레이드 배포 단계를 정의하는 클래스를 만듭니다.  배포 단계를 정의하기 위해 클래스에서는 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> 인터페이스를 구현합니다.  사용자 지정 배포 단계를 정의하려는 경우 이 인터페이스를 구현합니다.  
  
#### 사용자 지정 배포 단계를 정의하려면  
  
1.  에 있는  **DeploymentStepExtension** 프로젝트, UpgradeStep 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
    > [!NOTE]  
    >  때이 코드를 추가 하 여, 프로젝트 일부 컴파일 오류가 있지만 없어질 것 후 코드 이후 단계에서 추가 합니다.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/CS/deploymentstepextension/upgradestep.cs#1)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/vb/deploymentstepextension/upgradestep.vb#1)]  
  
## 사용자 지정 배포 단계가 포함된 배포 구성 만들기  
 새 업그레이드 배포 단계와 여러 개의 기본 제공 배포 단계가 포함 된 새 배포 구성에 대 한 프로젝트 확장을 만듭니다.  이 확장을 작성 하 여 SharePoint 개발자가 SharePoint 프로젝트에서 업그레이드 배포 단계를 사용 하는 데 도움이.  
  
 배포 구성을 만들기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스를 구현합니다.  SharePoint 프로젝트 확장을 만들려는 경우 이 인터페이스를 구현합니다.  
  
#### 배포 구성을 만들려면  
  
1.  에 있는  **DeploymentStepExtension** 프로젝트, DeploymentConfigurationExtension 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/CS/deploymentstepextension/deploymentconfigurationextension.cs#2)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/vb/deploymentstepextension/deploymentconfigurationextension.vb#2)]  
  
## 사용자 지정 SharePoint 명령 만들기  
 에 대 한 SharePoint 서버 개체 모델을 호출 하는 두 사용자 지정 명령을 만듭니다.  한 명령은 솔루션이 이미 배포되었는지 여부를 확인하고, 다른 명령은 솔루션을 업그레이드합니다.  
  
#### SharePoint 명령을 정의하려면  
  
1.  에 있는  **SharePointCommands** 프로젝트 명령 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/CS/SharePointCommands/Commands.cs#4)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/vb/sharepointcommands/commands.vb#4)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 사용자 지정 배포 단계와 SharePoint 명령을 위한 모든 코드가 프로젝트에 포함되었습니다.  빌드를 오류 없이 컴파일되는지 확인 합니다.  
  
#### 프로젝트를 빌드하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는  **DeploymentStepExtension** 프로젝트를 하 고 선택  **빌드**.  
  
2.  바로 가기 메뉴를 열고를  **SharePointCommands** 프로젝트를 하 고 선택  **빌드**.  
  
## 확장을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  첫째, VSIX 프로젝트에 있는 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다.  다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하고 만들려면  
  
1.  **솔루션 탐색기**아래에서  **UpgradeDeploymentStep** 프로젝트에 대 한 바로 가기 메뉴를 열고는  **source.extension.vsixmanifest** 파일을 및 다음 선택  **열기**.  
  
     매니페스트 편집기에서 파일이 열립니다.  Source.extension.vsixmanifest 파일이 모든 VSIX 패키지를 요구 하는 extension.vsixmanifest 파일에 대 한 기반이 됩니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  에 있는  **제품명** 상자에 입력  **업그레이드 배포 단계를 SharePoint 프로젝트에 대 한**.  
  
3.  에 있는  **작성자** 상자에 입력  **Contoso**.  
  
4.  에 있는  **설명이** 상자에 입력  **SharePoint 프로젝트에 사용할 수 있는 사용자 지정 업그레이드 배포 단계 제공**.  
  
5.  에  **자산** 탭 편집기의 선택은  **New** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
6.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
7.  에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
8.  에  **프로젝트** 목록에서 선택  **DeploymentStepExtension**, 다음 선택은  **확인** 단추입니다.  
  
9. 매니페스트 편집기에서 선택 된  **New** 단추를 다시 클릭 합니다.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
10. 에 있는  **유형** 목록에서 입력  **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  이 요소는 Visual Studio 확장에 포함할 사용자 지정 확장을 지정합니다.  자세한 내용은 [자산 요소 \(VSX 스키마\)](http://msdn.microsoft.com/ko-kr/9fcfc098-edc7-484b-9d4c-acd17829d737)을 참조하십시오.  
  
11. 에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
12. 에  **프로젝트** 목록에서 선택  **SharePointCommands**, 다음 선택은  **확인** 단추입니다.  
  
13. 메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**, 및 다음 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
14. UpgradeDeploymentStep 프로젝트의 빌드 출력 폴더에 이제 UpgradeDeploymentStep.vsix 파일이 들어 있는지 확인 합니다.  
  
     기본적으로 빌드 출력 경로는 프로젝트 파일이 포함된 폴더 아래에 있는 ..  \\bin\\Debug 폴더입니다.  
  
## 업그레이드 배포 단계 테스트 준비  
 업그레이드 배포 단계를 테스트하려면 먼저 SharePoint 사이트에 샘플 솔루션을 배포해야 합니다.  제일 먼저 실험 모드의 Visual Studio 인스턴스에서 확장을 디버깅합니다.  목록 정의와 목록 인스턴스를 배포 단계를 테스트 하는 데를 만들고 SharePoint 사이트에 배포 합니다.  그런 다음 목록 정의와 목록 인스턴스를 수정 하 고 어떻게 기본 배포 프로세스 솔루션에는 SharePoint 사이트를 덮어씁니다 보려면 다시 배포.  
  
 이 연습의 뒷부분에서 목록 정 및 목록 인스턴스를 수정 합니다 및 다음 SharePoint 사이트에 업그레이드 하겠습니다.  
  
#### 확장 디버깅을 시작하려면  
  
1.  Visual Studio 관리자 자격 증명으로 다시 시작 하 고 UpgradeDeploymentStep 솔루션을 엽니다.  
  
2.  DeploymentStepExtension 프로젝트에 UpgradeStep 코드 파일을 열고 다음 코드의 첫째 줄에 중단점을 추가 된 `CanExecute` 및 `Execute` 방법.  
  
3.  선택, F5 키를 선택 하 여 또는 메뉴 모음에서 디버깅 시작  **디버깅**,  **디버깅 시작**.  
  
4.  Visual Studio 확장에 대 한 SharePoint Projects\\1.0 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0Exp\\Extensions\\Contoso\\Upgrade 배포 단계를 설치 및 Visual Studio 실험 인스턴스를 시작.  Visual Studio이 인스턴스를 업그레이드 배포 단계를 테스트 합니다.  
  
#### 목록 정의와 목록 인스턴스를 SharePoint 프로젝트를 만들려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **파일**,  **New**,  **프로젝트**.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장의  **C\#** 노드 또는  **Visual Basic** 노드를 확장은  **SharePoint** 노드를 다음 선택의  **2010** 노드.  
  
3.  대화 상자의 상단에 있는지 확인  **.NET Framework 3.5** .NET Framework 버전의 목록에 나타납니다.  
  
     [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]용 프로젝트에는 이 .NET Framework 버전이 필요합니다.  
  
4.  프로젝트 템플릿 목록에서 선택  **SharePoint 2010 프로젝트**, 프로젝트의 이름을  **EmployeesListDefinition**, 다음 선택은  **확인** 단추입니다.  
  
5.  에  **SharePoint 사용자 지정 마법사**을 디버깅에 사용 하려는 사이트의 URL을 입력 합니다.  
  
6.  아래  **이란이 SharePoint 솔루션의 신뢰 수준을**, 선택은  **팜 솔루션으로 배포** 옵션 단추.  
  
    > [!NOTE]  
    >  업그레이드 배포 단계는 샌드박스가 적용 된 솔루션을 지원 하지 않습니다.  
  
7.  선택 된  **마침** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]EmployeesListDefinition 프로젝트를 만듭니다.  
  
8.  EmployeesListDefinition 프로젝트에 대 한 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 항목**.  
  
9. 에  **새 항목 추가\-EmployeesListDefinition** 대화 상자에서 확장은  **SharePoint** 노드를 다음 선택은  **2010** 노드.  
  
10. 선택은  **목록** : 항목 이름, 항목 템플릿이  **직원 목록**, 다음 선택은  **추가** 단추.  
  
     SharePoint 사용자 지정 마법사를 표시합니다.  
  
11. 에  **선택 목록 설정** 페이지에서 다음 설정을 확인 한 다음 선택은  **마침** 단추:  
  
    1.  **직원 목록** 표시 된  **이름을 목록에 표시 하 시겠습니까?** 상자.  
  
    2.  **기반으로 사용자 지정 목록 만들기:** 옵션 단추를 선택 합니다.  
  
    3.  **기본 \(비어 있음\)** 에 선택은  **기반으로 사용자 지정 목록 만들기:** 목록.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]직원 목록 항목 제목 열 및 빈 인스턴스가 만들어 목록 디자이너가 열립니다.  
  
12. 목록 디자이너에서에  **열** 탭에서 선택의  **기존 또는 새 열 이름 입력** 행을 하 고 다음 열에 추가  **열의 표시 이름** 목록:  
  
    1.  첫 번째 이름  
  
    2.  회사  
  
    3.  근무처 전화  
  
    4.  전자 메일  
  
13. 모든 파일을 저장 하 고 목록의 디자이너를 닫습니다.  
  
14. **솔루션 탐색기**, 확장은  **직원 목록** 노드를 차례로 확장 하 고는  **직원 목록 인스턴스** 자식 노드.  
  
15. Elements.xml 파일에 기본을 XML이 파일에서 다음 XML로 바꿉니다.  이 XML 목록에 이름을 변경  **직원** Jim Hance 명명 된 직원에 대 한 정보를 추가 합니다.  
  
    ```  
  
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
  
16. 저장 한 Elements.xml 파일을 닫습니다.  
  
17. EmployeesListDefinition 프로젝트에 대 한 바로 가기 메뉴를 열고 선택  **열기** 또는  **속성이**.  
  
     속성 디자이너가 열립니다.  
  
18. 에  **SharePoint** 탭을 지우기는  **디버깅 후 자동 취소** 확인란을 선택한 다음 등록 정보를 저장 합니다.  
  
#### 목록 정의와 목록 인스턴스를 배포하려면  
  
1.  **솔루션 탐색기**, 선택은  **EmployeesListDefinition** 프로젝트 노드.  
  
2.  **속성** 창에서 **활성 배포 구성** 속성이 **기본값**으로 설정되어 있는지 확인합니다.  
  
3.  F5 키를 선택 하거나 메뉴 표시줄에서 선택  **디버깅**,  **디버깅 시작**.  
  
4.  프로젝트가 성공적으로 빌드, 웹 브라우저에서 SharePoint 사이트에 열린다는 것을 확인 하는  **나열** 새 빠른 실행 표시줄에서 항목을 포함  **직원** 목록 및 해당의  **직원** 목록 Jim Hance의 항목을 포함.  
  
5.  웹 브라우저를 닫습니다.  
  
#### 목록 정의와 목록 인스턴스를 수정하고 다시 배포하려면  
  
1.  EmployeesListDefinition 프로젝트의 자식입니다의 Elements.xml 파일 열기는  **직원 목록 인스턴스의** 프로젝트 항목입니다.  
  
2.  `Data` 요소와 해당 자식 요소를 제거하여 목록에서 Jim Hance의 항목을 제거합니다.  
  
     완료 되 면 다음과 같은 XML 파일이 있어야 합니다.  
  
    ```  
  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
      </ListInstance>  
    </Elements>  
    ```  
  
3.  저장 한 Elements.xml 파일을 닫습니다.  
  
4.  바로 가기 메뉴를 열고를  **직원 목록** 프로젝트 항목을 및 다음 선택  **열기** 또는  **속성**.  
  
5.  목록 디자이너의 선택에서  **보기** 탭입니다.  
  
6.  에  **선택한 열** 목록에서 선택  **첨부 파일**, 다음 선택은 \< 해당 열으로 이동 하려면 키를  **사용 가능한 열** 목록입니다.  
  
7.  이동 하려면 이전 단계를 반복의  **비즈니스 전화** 열에서의  **선택한 열** 목록에  **사용 가능한 열** 목록.  
  
     이 작업을 수행하면 SharePoint 사이트에 있는 **Employees** 목록의 기본 뷰에서 해당 필드가 제거됩니다.  
  
8.  선택, F5 키를 선택 하 여 또는 메뉴 모음에서 디버깅 시작  **디버깅**,  **디버깅 시작**.  
  
9. **배포 충돌** 대화 상자가 나타나는지 확인합니다.  
  
     Visual Studio \(목록 인스턴스\) 솔루션을 배포 하려고 할 때이 대화 상자에 해당 솔루션이 이미 배포 된 SharePoint 사이트에 표시 됩니다.  이 연습의 뒷부분에서 업그레이드 배포 단계를 실행 하는 경우이 대화 상자가 나타나지 않습니다.  
  
10. 에  **배포 충돌** 대화 상자에서 선택 된  **자동 해결** 옵션 단추.  
  
     Visual Studio SharePoint 사이트에서 목록 인스턴스가 삭제 목록 항목에는 프로젝트를 배포 하 고 그런 다음 SharePoint 사이트를 엽니다.  
  
11. 에  **나열** 섹션 빠른 실행 표시줄의 선택은  **직원** 목록 및 다음 다음과 같은 세부 정보를 확인:  
  
    -   **첨부 파일** 및  **집 전화** 열이 목록이 보기에 나타나지 않습니다.  
  
    -   목록이 비어 있습니다.  **기본** 배포 구성을 사용하여 솔루션을 다시 배포한 경우 **Employees** 목록이 프로젝트의 새로운 빈 목록으로 바뀌었습니다.  
  
## 배포 단계 테스트  
 이제 업그레이드 배포 단계를 테스트할 준비가 되었습니다.  제일 먼저 SharePoint의 목록 인스턴스에 항목을 추가합니다.  그런 다음 목록 정의와 목록 인스턴스를 변경 하 고 SharePoint 사이트에서 업그레이드할 업그레이드 배포 단계에서 새 항목을 덮어쓰지 확인 합니다.  
  
#### 목록에 항목을 수동으로 추가하려면  
  
1.  리본에는 SharePoint 사이트에서 아래는  **목록 도구** 탭에서 선택 된  **항목** 탭.  
  
2.  에  **New** 선택, 그룹  **새 항목**.  
  
     선택할 수 있는  **새 항목 추가** 항목 목록의 링크를에서 합니다.  
  
3.  에 있는  **직원 – 새 항목** 창에서의  **제목** 상자에 입력  **시설 관리자**.  
  
4.  에 있는  **성** 상자에 입력  **Andy**.  
  
5.  에 있는  **회사** 상자에 입력  **Contoso**.  
  
6.  선택 된  **저장** 단추를 새 항목을 목록에 나타나는지 확인 하 고 다음 웹 브라우저를 닫습니다.  
  
     이 연습의 뒷부분에서 업그레이드 배포 단계를이 목록의 내용을 덮어쓰지 확인 하려면이 항목을 사용 합니다.  
  
#### 업그레이드 배포 단계를 테스트하려면  
  
1.  실험적 인스턴스에서 Visual Studio  **솔루션 탐색기**, 바로 가기 메뉴를 열고는  **EmployeesListDefinition** 프로젝트 노드 및 다음 선택  **속성**.  
  
     등록 정보 편집기\/디자이너가 열립니다.  
  
2.  에  **SharePoint** 탭에서 설정 된  **활성 배포 구성** 속성을  **업그레이드**.  
  
     이 사용자 지정 배포 구성은 새 업그레이드 배포 단계가 포함 되어 있습니다.  
  
3.  바로 가기 메뉴를 열고를  **직원 목록** 프로젝트 항목을 및 다음 선택  **속성** 또는  **열기**.  
  
     등록 정보 편집기\/디자이너가 열립니다.  
  
4.  에  **보기** 탭에서 선택의  **전자** 열 다음 선택의  **\<** 키에서 열을 이동 합니다는  **선택한 열** 나열 하는  **사용 가능한 열** 목록.  
  
     이 작업을 수행하면 SharePoint 사이트에 있는 **Employees** 목록의 기본 뷰에서 해당 필드가 제거됩니다.  
  
5.  선택, F5 키를 선택 하 여 또는 메뉴 모음에서 디버깅 시작  **디버깅**,  **디버깅 시작**.  
  
6.  다른 Visual Studio 인스턴스의 코드가 이전에 `CanExecute` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  
  
7.  F5 키를 다시 선택 하거나 메뉴 표시줄에서 선택  **디버깅**,  **계속**.  
  
8.  코드가 이전에 `Execute` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  
  
9. F5 키를 선택 하거나 메뉴 표시줄에서 선택  **디버깅**,  **계속** 를 마지막으로 합니다.  
  
     웹 브라우저에서 SharePoint 사이트를 엽니다.  
  
10. 에  **나열** 섹션 빠른 실행 영역에 선택은  **직원** 목록 및 다음 다음과 같은 세부 정보를 확인 합니다:  
  
    -   앞부분 \(Andy 대를 시설 관리자\) 수동으로 추가한 항목 아직 목록에 있습니다.  
  
    -   **회사 전화** 및  **메일 주소** 열이 목록이 보기에 나타나지 않습니다.  
  
     **업그레이드** 배포 구성은 SharePoint 사이트의 기존 **Employees** 목록 인스턴스를 수정합니다.  **업그레이드** 구성 대신 **기본** 배포 구성을 사용한 경우 배포 충돌이 발생합니다.  Visual Studio 교체 하 여 충돌을 해결 하는  **직원** 목록 및 항목에 Andy, 시설 관리자, 삭제할 수 있습니다.  
  
## 개발 컴퓨터 정리  
 업그레이드 배포 단계의 테스트를 마쳤으면 SharePoint 사이트에서 목록 인스턴스와 목록 정의를 제거하고 Visual Studio에서 배포 단계 확장을 제거합니다.  
  
#### SharePoint 사이트에서 목록 인스턴스를 제거하려면  
  
1.  열은  **직원** 목록을 SharePoint 사이트에 목록이 아직 열려 있지 않은 경우.  
  
2.  SharePoint 사이트에서 리본 메뉴에 선택은  **목록 도구** 탭을 클릭 한 다음 선택은  **목록** 탭.  
  
3.  에  **설정** 그룹, 선택은  **목록 설정** 항목.  
  
4.  아래  **사용 권한 및 관리**, 선택은  **이 목록 삭제** 명령에서 선택  **확인** 목록 휴지통으로 보내고 다음 웹 브라우저를 닫을 것인지 확인 하.  
  
#### SharePoint 사이트에서 목록 정의를 제거하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **빌드**,  **리트랙트**.  
  
     SharePoint 사이트에서 목록 정의가 제거됩니다.  
  
#### 확장을 제거하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **도구**,  **확장 및 업데이트**.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장명 목록에서 선택한  **업그레이드 배포 단계를 SharePoint 프로젝트에 대 한**, 다음 선택은  **제거** 명령입니다.  
  
3.  나타나는 대화 상자에서 선택한  **예** 확장명을 제거 하 고 선택 확인 합니다  **이제 다시** 제거를 완료 합니다.  
  
4.  Visual Studio \(Visual Studio UpgradeDeploymentStep 솔루션에 열려 있는 인스턴스 및 실험적 인스턴스\)을 모두 닫습니다.  
  
## 참고 항목  
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  