---
title: "Defining Custom SharePoint Project Item Types"
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
ms.assetid: be300c24-fd1b-4fc7-a4e9-a5df1d81d3fc
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# Defining Custom SharePoint Project Item Types
  새로운 종류의 SharePoint 프로젝트 항목을 만들려는 경우 새 SharePoint 프로젝트 항목 형식을 정의합니다.  예를 들어 Visual Studio에는 필드 또는 사용자 지정 작업을 SharePoint 사이트에 추가하기 위한 SharePoint 프로젝트 항목이 포함되어 있지 않습니다.  그러나 필드, 사용자 지정 작업 또는 다른 유형의 SharePoint 구성 요소를 만들기 위해 고유한 SharePoint 프로젝트 항목 형식을 직접 정의할 수 있습니다.  
  
## SharePoint 프로젝트 항목 형식을 정의하기 위한 작업  
 사용자 지정 프로젝트 항목 형식을 정의하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 Visual Studio Extension 어셈블리를 빌드합니다.  자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)을 참조하십시오.  
  
 사용자 지정 프로젝트 항목 형식을 정의하는 경우 프로젝트 항목에 다음 기능을 추가할 수도 있습니다.  
  
-   프로젝트 항목에 바로 가기 메뉴 항목을 추가합니다.  프로젝트 항목에 대 한 바로 가기 메뉴를 열 때 메뉴 항목이 나타납니다  **솔루션 탐색기** 프로젝트 항목을 마우스 오른쪽 단추로 클릭 하거나 선택 하 여 및 다음 Shift \+ f10 키를 선택 키입니다.  자세한 내용은 [How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)을 참조하십시오.  
  
-   프로젝트 항목에 사용자 지정 속성을 추가합니다.  속성 표시는  **속성** 에서 프로젝트 항목을 선택 하면 창  **솔루션 탐색기**.  자세한 내용은 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)을 참조하십시오.  
  
 Visual Studio에서 다른 개발자가 프로젝트 항목을 사용할 수 있도록 하려면 .spdata 파일을 만들고 해당 프로젝트 항목과 연결된 항목 템플릿 또는 프로젝트 템플릿을 만듭니다.  자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)을 참조하십시오.  
  
## 프로젝트 항목 형식 및 프로젝트 항목 인스턴스 간 관계 이해  
 SharePoint 프로젝트 항목 형식을 정의하는 경우 연결된 형식의 프로젝트 항목을 SharePoint 프로젝트에 추가하면 확장이 로드됩니다.  예를 들어 새 **사용자 지정 작업** 프로젝트 항목 형식을 정의하는 경우 사용자가 **사용자 지정 작업** 프로젝트 항목을 프로젝트에 추가하면 확장이 로드됩니다.  연결된 프로젝트 항목 형식의 모든 인스턴스에 대해 같은 확장 인스턴스가 사용됩니다.  앞의 예제에서 사용자가 두 번째 **사용자 지정 작업** 프로젝트 항목을 프로젝트에 추가하는 경우 두 번째 프로젝트 항목을 사용자 지정하는 데 같은 확장 인스턴스가 사용됩니다.  
  
 프로젝트 항목 형식의 특정 인스턴스에 액세스하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드의 구현에서 *projectItemTypeDefinition* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 이벤트 중 하나를 처리합니다.  예를 들어 사용자 지정 형식의 프로젝트 항목을 프로젝트에 추가하는 시기를 결정하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 이벤트를 처리합니다.  자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  