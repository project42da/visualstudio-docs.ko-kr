---
title: "How to: Handle Deployment Conflicts"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, extending deployment"
ms.assetid: 8e545873-3fed-46cf-a95f-27b5fc0d5f83
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# How to: Handle Deployment Conflicts
  SharePoint 프로젝트 항목에 대한 배포 충돌을 처리하는 사용자 고유의 코드를 제공할 수 있습니다.  예를 들어, 현재 프로젝트 항목의 파일이 배포 위치에 이미 있는지 여부를 확인한 다음 현재 프로젝트 항목이 배포되기 전에 배포된 파일을 삭제할 수 있습니다.  배포 충돌에 대한 자세한 내용은 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)을 참조하십시오.  
  
### 배포 충돌을 처리하려면  
  
1.  프로젝트 항목 확장, 프로젝트 확장 또는 새 프로젝트 항목 형식의 정의를 만듭니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
    -   [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  확장에서 프로젝트 항목 확장이나 프로젝트 확장에 있는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> 개체 또는 새 프로젝트 항목 형식의 정의에 있는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 이벤트를 처리합니다.  
  
3.  이벤트 처리기에서 해당 시나리오에 적용되는 기준에 따라, 배포될 프로젝트 항목과 SharePoint 사이트의 배포된 솔루션 간에 충돌이 있는지 여부를 확인합니다.  이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemEventArgs.ProjectItem%2A> 속성을 사용하여 배포될 프로젝트 항목을 분석할 수 있으며, 이 용도로 정의한 SharePoint 명령을 호출하여 배포 위치의 파일을 분석할 수 있습니다.  
  
     다양한 유형의 충돌에 대해 먼저 실행 중인 배포 단계를 확인하려고 할 수 있습니다.  이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.DeploymentStepInfo%2A> 속성을 사용하여 이 작업을 수행할 수 있습니다.  일반적으로 기본 제공 <xref:Microsoft.VisualStudio.SharePoint.Deployment.DeploymentStepIds.AddSolution> 배포 단계 중에 충돌을 검색하는 것이 적합하지만 어떠한 배포 단계 중에도 충돌을 확인할 수 있습니다.  
  
4.  충돌이 있는 경우 이벤트 인수의 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.Conflicts%2A> 속성에 대한 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> 메서드를 사용하여 새 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> 개체를 만듭니다.  이 개체는 배포 충돌을 나타냅니다.  <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> 메서드 호출에서 충돌을 해결하기 위해 호출되는 메서드도 지정합니다.  
  
## 예제  
 다음 코드 예제에서는 목록 정의 프로젝트 항목의 프로젝트 항목 확장에서 배포 충돌을 처리하기 위한 기본 프로세스를 보여 줍니다.  다른 프로젝트 항목 형식에 대한 배포 충돌을 처리하려면 다른 문자열을 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>에 전달합니다.  자세한 내용은 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)을 참조하십시오.  
  
 편의상 이 예제의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 이벤트 처리기에서는 배포 충돌이 있다고 가정하며\(즉, 항상 새 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> 개체를 추가함\), `Resolve` 메서드는 충돌이 해결되었음을 나타내기 위해 간단히 **true**를 반환합니다.  실제 시나리오의 경우 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 이벤트 처리기는 먼저 현재 프로젝트 항목의 파일과 배포 위치의 파일 간에 충돌이 있는지 여부를 확인한 다음 충돌이 있는 경우에만 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> 개체를 추가합니다.  예를 들어, 이벤트 처리기에서 `e.ProjectItem.Files` 속성을 사용하여 프로젝트 항목의 파일을 분석할 수 있으며, SharePoint 명령을 호출하여 배포 위치의 파일을 분석할 수도 있습니다.  마찬가지로 실제 시나리오에서는 `Resolve` 메서드가 SharePoint 명령을 호출하여 SharePoint 사이트의 충돌을 해결할 수 있습니다.  SharePoint 명령을 만드는 방법에 대한 자세한 내용은 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md)를 참조하십시오.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.deploymentconflict/cs/extension/deploymentconflictextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.deploymentconflict/vb/extension/deploymentconflictextension.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)   
 [How to: Run Code When Deployment Steps are Executed](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md)  
  
  