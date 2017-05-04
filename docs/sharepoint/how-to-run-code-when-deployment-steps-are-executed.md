---
title: "How to: Run Code When Deployment Steps are Executed | Microsoft Docs"
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
  - "SharePoint development in Visual Studio, extending deployment"
ms.assetid: 6b0a52e5-e0ba-41bc-9e8a-1013e51fd3ba
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# How to: Run Code When Deployment Steps are Executed
  SharePoint 프로젝트의 배포 단계에 대해 추가 작업을 수행하려는 경우 Visual Studio에서 각 배포 단계를 실행하기 전후에 SharePoint 프로젝트 항목에서 발생하는 이벤트를 처리할 수 있습니다.  자세한 내용은 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)을 참조하십시오.  
  
### 배포 단계가 진행될 때 코드를 실행하려면  
  
1.  프로젝트 항목 확장, 프로젝트 확장 또는 새 프로젝트 항목 형식의 정의를 만듭니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
    -   [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  확장에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> 개체\(프로젝트 항목 또는 프로젝트를 확장하는 경우\) 또는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> 개체\(새 프로젝트 항목 형식을 정의하는 경우\)의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> 이벤트를 처리합니다.  
  
3.  이벤트 처리기에서 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> 및 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> 매개 변수를 사용하여 배포 단계에 대한 정보를 가져옵니다.  예를 들어 실행 중인 배포 단계와 솔루션이 배포되는지 또는 제거되는지를 확인할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 목록 인스턴스 프로젝트 항목의 확장에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> 이벤트를 처리하는 방법을 보여 줍니다.  이 확장은 Visual Studio에서 솔루션을 배포 및 제거하는 동안 응용 프로그램 풀을 재생할 때 **출력** 창에 추가 메시지를 씁니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/handledeploymentstepevents.cs#4)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/handledeploymentstepevents.vb#4)]  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [How to: Run Code When a SharePoint Project is Deployed or Retracted](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)  
  
  