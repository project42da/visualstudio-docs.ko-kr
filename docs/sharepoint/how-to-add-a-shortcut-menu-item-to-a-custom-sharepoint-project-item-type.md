---
title: "How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type | Microsoft Docs"
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
  - "SharePoint project items, defining your own types"
  - "project items [SharePoint development in Visual Studio], defining your own types"
  - "SharePoint development in Visual Studio, defining new project item types"
ms.assetid: f6ec47a7-e7d9-4e26-810b-77943a1ab04c
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의하는 경우 프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수 있습니다.  메뉴 항목은 **솔루션 탐색기**에서 해당 프로젝트 항목을 사용자가 마우스 오른쪽 단추로 클릭하면 나타납니다.  
  
 다음 단계에서는 사용자 고유의 SharePoint 프로젝트 항목 형식이 이미 정의되어 있는 것으로 가정합니다.  자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)을 참조하십시오.  
  
### 사용자 지정 프로젝트 항목 형식에 바로 가기 메뉴 항목을 추가하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드에서 *projectItemTypeDefinition* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트를 처리합니다.  
  
2.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트의 이벤트 처리기에서 새 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체를 이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> 컬렉션에 추가합니다.  
  
3.  에 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 새에 대 한 이벤트 처리기를 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체를 사용자가 바로 가기 메뉴 항목을 선택할 때 실행할 작업을 수행 합니다.  
  
## 예제  
 다음 코드 예제에서는 상황에 맞는 메뉴 항목을 사용자 지정 프로젝트 항목 형식에 추가하는 방법을 보여 줍니다.  열 때 바로 가기 메뉴에서 프로젝트 항목을  **솔루션 탐색기** 선택은  **출력 창에 메시지 쓰기** 메뉴 항목을 Visual Studio 메시지를 표시는  **출력** 창.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/cs/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/vb/extension/projectitemtypemenu.vb#4)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 **출력t** 창에 메시지를 작성합니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 있는 클래스 라이브러리 프로젝트가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 하려면 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다.  자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)을 참조하십시오.  
  
 프로젝트 항목을 배포하려면 어셈블리, 템플릿 및 프로젝트 항목과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  