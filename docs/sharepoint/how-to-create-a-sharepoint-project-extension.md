---
title: "How to: Create a SharePoint Project Extension"
ms.custom: ""
ms.date: "04/28/2017"
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
  - "projects [SharePoint development in Visual Studio], extending"
  - "SharePoint development in Visual Studio, extending projects"
  - "SharePoint projects, extending"
ms.assetid: ceecb9cb-4a5d-44c9-992f-9624737ac996
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# How to: Create a SharePoint Project Extension
  Visual Studio에서 열려 있는 SharePoint 프로젝트에 기능을 추가하려는 경우 프로젝트 확장을 만듭니다.  자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
### 프로젝트 확장을 만들려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 <xref:System.ComponentModel.Composition.ExportAttribute>를 추가합니다.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 형식을 특성 생성자에 전달합니다.  
  
5.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 메서드 구현에서 *projectService* 매개 변수의 멤버를 사용하여 확장의 동작을 정의합니다.  이 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> 인터페이스에 정의된 이벤트에 대한 액세스를 제공하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체입니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> 인터페이스를 통해 정의되는 대부분의 SharePoint 프로젝트 이벤트를 처리하는 간단한 프로젝트 확장을 만드는 방법을 보여 줍니다.  이 코드를 테스트하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 만든 다음 솔루션에 프로젝트를 추가하고, 프로젝트 속성 값을 변경하거나 프로젝트를 삭제 또는 제외합니다.  확장에서는 **출력** 창 및 **오류 목록** 창에 메시지를 작성하여 사용자에게 이벤트를 알려 줍니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#3](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/projectextension.cs#3)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/projectextension.vb#3)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/savedatatoprojectfile.vb#3)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 **출력** 창과 **오류 목록** 창에 메시지를 씁니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> 이벤트를 처리하는 방법을 보여 주는 예제는 [How to: Add a Shortcut Menu Item to SharePoint Projects](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md) 및 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)   
 [How to: Add a Shortcut Menu Item to SharePoint Projects](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Walkthrough: Creating a SharePoint Project Extension](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)  
  
  