---
title: "How to: Execute a SharePoint Command"
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
  - "SharePoint commands [SharePoint development in Visual Studio], executing"
ms.assetid: 2d1a163b-b601-4dac-bcea-328f24cb4d57
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# How to: Execute a SharePoint Command
  SharePoint 도구 확장에서 서버 개체 모델을 사용하려면 API를 호출하는 사용자 지정 *SharePoint 명령*을 만들어야 합니다.  명령을 정의하고 SharePoint 도구 확장을 사용하여 배포하면 확장에서 해당 명령을 실행하여 SharePoint 서버 개체 모델을 호출할 수 있습니다.  명령을 실행하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체의 ExecuteCommand 메서드 중 하나를 사용합니다.  
  
 SharePoint 명령의 용도에 대한 자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
### SharePoint 명령을 실행하려면  
  
1.  SharePoint 도구 확장에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection>을 가져옵니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체를 가져오는 방법은 만들려는 확장 형식에 따라 달라집니다.  
  
    -   SharePoint 프로젝트 시스템 확장에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.SharePointConnection%2A> 속성을 사용합니다.  
  
         프로젝트 시스템 확장에 대한 자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
    -   **서버 탐색기**의 **SharePoint 연결** 노드 확장에서는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext.SharePointConnection%2A> 속성을 사용합니다.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext> 개체를 가져오려면 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.Context%2A> 속성을 사용합니다.  
  
         **서버 탐색기** 확장에 대한 자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
    -   프로젝트 템플릿 마법사 등의 SharePoint 도구 확장에 포함되지 않는 코드에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A> 속성을 사용합니다.  
  
         프로젝트 서비스 검색에 대한 자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
2.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체의 ExecuteCommand 메서드 중 하나를 호출합니다.  실행할 명령 이름을 ExecuteCommand 메서드의 첫 번째 인수에 전달합니다.  명령에 사용자 지정 매개 변수가 있으면 해당 매개 변수를 ExecuteCommand 메서드의 두 번째 인수에 전달합니다.  
  
     지원되는 각 명령 시그니처마다 다른 ExecuteCommand 오버로드가 있습니다.  다음 표에서는 지원되는 서명과 각 서명에 사용할 오버로드를 보여 줍니다.  
  
    |명령 시그니처|사용할 ExecuteCommand 오버로드|  
    |-------------|-----------------------------|  
    |명령에 기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수만 있고 반환 값이 없습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |명령에 기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수와 반환 값이 있습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |명령에 두 개의 매개 변수\(기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수 및 사용자 지정 매개 변수\)가 있고 반환 값이 없습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |명령에 두 개의 매개 변수와 반환 값이 있습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
  
## 예제  
 다음 코드 예제에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> 오버로드를 사용하여 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md)에서 설명된 `Contoso.Commands.UpgradeSolution` 명령을 호출하는 방법을 보여 줍니다.  
  
 [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/CS/deploymentstepextension/upgradestep.cs#6)]
 [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/vb/deploymentstepextension/upgradestep.vb#6)]  
  
 이 예제에 나와 있는`Execute` 메서드는 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> 인터페이스의 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep.Execute%2A> 메서드를 사용자 지정 배포 단계에서 구현한 것입니다.  보다 큰 예제의 컨텍스트에서 이 코드를 보려면 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)를 참조하십시오.  
  
 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> 메서드 호출에 대해 다음 세부 정보를 확인합니다.  
  
-   첫 번째 매개 변수는 호출할 명령을 식별합니다.  이 문자열은 명령 정의의 <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute>에 전달하는 값과 일치합니다.  
  
-   두 번째 매개 변수는 명령의 두 번째 사용자 지정 매개 변수에 전달할 값입니다.  이 예제에서 두 번째 매개 변수는 SharePoint 사이트로 업그레이드될 .wsp 파일의 전체 경로입니다.  
  
-   암시적 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수는 코드를 통해 명령에 전달되지 않습니다.  이 매개 변수는 SharePoint 프로젝트 시스템의 확장이나 **서버 탐색기**의 **SharePoint 연결** 노드 확장에서 명령을 호출할 때 자동으로 명령에 전달됩니다.  <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 프로젝트 템플릿 마법사 등의 기타 솔루션 형식에서는 이 매개 변수가 **null**입니다.  
  
## 코드 컴파일  
 이 예제에서는 Microsoft.VisualStudio.SharePoint 어셈블리에 대한 참조가 필요합니다.  
  
## 참고 항목  
 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
  