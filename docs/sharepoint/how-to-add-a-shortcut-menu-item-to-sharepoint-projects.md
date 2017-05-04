---
title: "How to: Add a Shortcut Menu Item to SharePoint Projects | Microsoft Docs"
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
  - "projects [SharePoint development in Visual Studio], extending"
  - "SharePoint development in Visual Studio, extending projects"
  - "SharePoint projects, extending"
ms.assetid: bb251fe9-f1bf-4ddd-9359-4b7f78fbd50f
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 8
---
# How to: Add a Shortcut Menu Item to SharePoint Projects
  SharePoint 프로젝트에 바로 가기 메뉴 항목을 추가할 수 있습니다.  이 메뉴 항목은 사용자가 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하면 나타납니다.  
  
 다음 단계에서는 프로젝트 확장이 이미 만들어져 있는 것으로 가정합니다.  자세한 내용은 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)를 참조하십시오.  
  
### SharePoint 프로젝트에 바로 가기 메뉴 항목을 추가하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 구현의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 메서드에서 *projectService* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> 이벤트를 처리합니다.  
  
2.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> 이벤트의 이벤트 처리기에서 새 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체를 이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.ActionMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.AddMenuItems%2A> 컬렉션에 추가합니다.  
  
3.  사용자가 바로 가기 메뉴 항목을 클릭하면 실행되도록 할 작업을 새 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체의 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 이벤트 처리기에서 수행합니다.  
  
## 예제  
 다음 코드 예제에서는 **솔루션 탐색기**의 SharePoint 프로젝트 노드에 바로 가기 메뉴 항목을 추가하는 방법을 보여 줍니다.  사용자가 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **Write Message to Output Window** 메뉴 항목을 클릭하면 Visual Studio에서는 **출력** 창에 메시지를 표시합니다.  이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 메시지를 표시합니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
 [!code-csharp[SPExtensibility.ProjectExtension.Menu#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.menu/cs/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectExtension.Menu#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.menu/vb/extension/projectitemextensionmenu.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 있는 클래스 라이브러리 프로젝트가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending SharePoint Projects](../sharepoint/extending-sharepoint-projects.md)   
 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)  
  
  