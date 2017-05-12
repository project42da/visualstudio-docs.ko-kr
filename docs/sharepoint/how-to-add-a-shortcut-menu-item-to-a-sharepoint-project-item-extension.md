---
title: "How to: Add a Shortcut Menu Item to a SharePoint Project Item Extension"
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
  - "project items [SharePoint development in Visual Studio], extending"
  - "SharePoint project items, extending"
  - "SharePoint development in Visual Studio, extending project items"
ms.assetid: d00513a6-d66d-4fbe-9efa-ef3b08c9a73a
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# How to: Add a Shortcut Menu Item to a SharePoint Project Item Extension
  프로젝트 항목 확장을 사용하여 SharePoint 프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수 있습니다.  메뉴 항목은 **솔루션 탐색기**에서 해당 프로젝트 항목을 사용자가 마우스 오른쪽 단추로 클릭하면 나타납니다.  
  
 다음 단계에서는 프로젝트 항목 확장이 이미 만들어져 있는 것으로 가정합니다.  자세한 내용은 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)를 참조하십시오.  
  
### 프로젝트 항목 확장에서 바로 가기 메뉴 항목을 추가하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 구현의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드에서 *projectItemType* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트를 처리합니다.  
  
2.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트의 이벤트 처리기에서 새 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체를 이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> 컬렉션에 추가합니다.  
  
3.  사용자가 바로 가기 메뉴 항목을 클릭하면 실행되도록 할 작업을 새 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체의 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 이벤트 처리기에서 수행합니다.  
  
## 예제  
 다음 코드 예제에서는 이벤트 수신자 프로젝트 항목에 바로 가기 메뉴 항목을 추가하는 방법을 보여 줍니다.  사용자가 **솔루션 탐색기**에서 프로젝트 항목을 마우스 오른쪽 단추로 클릭하고 **출력 창에 메시지 쓰기** 메뉴 항목을 클릭하면 Visual Studio에서는 **출력** 창에 메시지를 표시합니다.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/cs/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/vb/extension/projectitemextensionmenu.vb#1)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 **출력t** 창에 메시지를 작성합니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 있는 클래스 라이브러리 프로젝트가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [How to: Add a Property to a SharePoint Project Item Extension](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)   
 [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  