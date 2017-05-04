---
title: "Converting Between SharePoint Project System Types and Other Visual Studio Project Types | Microsoft Docs"
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
  - "SharePoint project service"
ms.assetid: ad5d8ab2-1659-4e6a-8783-47e0dad44b11
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# Converting Between SharePoint Project System Types and Other Visual Studio Project Types
  SharePoint 프로젝트 시스템에 개체가 있는데 Visual Studio 자동화 개체 모델이나 통합 개체 모델의 해당 개체 기능을 사용하려는 경우나 그 반대의 경우가 있을 수 있습니다.  이러한 경우 SharePoint 프로젝트 서비스의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 메서드를 사용하여 개체를 다른 개체 모델로 변환할 수 있습니다.  
  
 예를 들어 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체가 있는데 <xref:EnvDTE.Project> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> 개체에서만 사용할 수 있는 메서드를 사용하려고 할 수 있습니다.  이 경우 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 메서드를 사용하여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>를 <xref:EnvDTE.Project> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>로 변환할 수 있습니다.  
  
 Visual Studio 자동화 개체 모델 및 Visual Studio 통합 개체 모델에 대한 자세한 내용은 [Overview of the Programming Model of SharePoint Tools Extensions](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)를 참조하십시오.  
  
## 변환 형식  
 다음 표에서는 이 메서드를 통해 SharePoint 프로젝트 시스템과 기타 Visual Studio 개체 모델 간에 변환할 수 있는 형식을 보여 줍니다.  
  
|SharePoint 프로젝트 시스템 형식|자동화 및 통합 개체 모델의 해당 형식|  
|----------------------------|---------------------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> 또는<br /><br /> 프로젝트에 대한 내부 COM 개체에서 구현되는 Visual Studio 통합 개체 모델의 모든 인터페이스.  이러한 인터페이스에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>\(또는 파생 인터페이스\) 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>가 포함됩니다.  프로젝트에서 구현되는 주요 인터페이스의 목록은 [프로젝트 모델에 대 한 핵심 구성 요소](../extensibility/internals/project-model-core-components.md)를 참조하십시오.|  
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> 또는<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>에서 해당 항목을 포함하는 프로젝트 멤버를 식별하는 <xref:System.UInt32> 값\(VSITEMID라고도 함\).  이 값은 일부 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 메서드의 *itemid* 매개 변수에 전달할 수 있습니다.|  
  
## 예제  
 다음 코드 예제에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 메서드를 사용하여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체를 <xref:EnvDTE.Project>로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromdte/cs/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromdte/vb/connect.vb#2)]  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   EnvDTE.dll 어셈블리에 대한 참조를 갖는 SharePoint 프로젝트 시스템의 확장.  자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> 이벤트를 처리할 `projectService_ProjectAdded` 메서드를 등록하는 코드.  예제를 보려면 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)를 참조하십시오.  
  
## 참고 항목  
 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)   
 [How to: Retrieve the SharePoint Project Service](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Overview of the Programming Model of SharePoint Tools Extensions](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  