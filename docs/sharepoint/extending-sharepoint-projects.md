---
title: "Extending SharePoint Projects"
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
ms.assetid: 4643012b-6e6c-4b7c-bb92-b04b34f6c715
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# Extending SharePoint Projects
  SharePoint 프로젝트의 프로젝트 수준 기능을 사용자 지정하려는 경우 프로젝트 확장을 만듭니다.  예를 들어 사용자 지정 프로젝트 속성을 추가하거나, 사용자가 Visual Studio에서 SharePoint 솔루션을 개발할 때 발생하는 프로젝트 수준 이벤트에 응답할 수 있습니다.  
  
## 프로젝트 확장 만들기  
 프로젝트 항목을 확장하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스를 구현하는 Visual Studio Extension 어셈블리를 빌드합니다.  자세한 내용은 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)을 참조하십시오.  
  
 프로젝트 확장을 만들 때 SharePoint 프로젝트에 다음 기능을 추가할 수도 있습니다.  
  
-   바로 가기 메뉴 항목을 추가합니다.  메뉴 항목의 SharePoint 프로젝트 노드에 대 한 바로 가기 메뉴를 열면 나타납니다  **솔루션 탐색기** 키 노드를 마우스 오른쪽 단추로 클릭 하거나 선택 하 여 및 다음 Shift \+ f 10을 선택으로.  자세한 내용은 [How to: Add a Shortcut Menu Item to SharePoint Projects](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)을 참조하십시오.  
  
-   사용자 지정 속성을 추가합니다.  속성 표시는  **속성이** SharePoint 프로젝트를 선택 하면 창  **솔루션 탐색기**.  자세한 내용은 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)을 참조하십시오.  
  
 프로젝트 확장을 만들고 배포 및 테스트하는 방법을 보여 주는 연습은 [Walkthrough: Creating a SharePoint Project Extension](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)을 참조하십시오.  
  
## 프로젝트 확장 및 프로젝트 인스턴스 간 관계 이해  
 프로젝트 확장을 만들면 종류에 관계없이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 열 때 확장이 로드됩니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 목록 정의, 콘텐츠 형식 및 이벤트 수신자 같은 여러 가지 SharePoint 프로젝트 템플릿이 포함되어 있습니다.  그러나 SharePoint 프로젝트 형식은 하나 밖에 없습니다.  **새 프로젝트** 대화 상자에 표시되는 프로젝트 형식은 하나 이상의 SharePoint 프로젝트 항목을 묶어 주는 템플릿뿐입니다.  SharePoint 프로젝트 형식은 하나 밖에 없기 때문에 한 프로젝트에 대해 만든 확장은 모든 SharePoint 프로젝트에 적용됩니다.  예를 들어 **콘텐츠 형식** 프로젝트 하나에만 적용되는 확장은 만들 수 없습니다.  
  
 특정 프로젝트 인스턴스에 액세스하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 메서드의 구현에서 *projectService* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> 이벤트 중 하나를 처리합니다.  예를 들어 SharePoint 프로젝트를 솔루션에 추가할 시기를 결정하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> 이벤트를 처리합니다.  자세한 내용은 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [How to: Add a Shortcut Menu Item to SharePoint Projects](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Walkthrough: Creating a SharePoint Project Extension](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)   
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  