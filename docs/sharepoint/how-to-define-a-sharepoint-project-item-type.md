---
title: "How to: Define a SharePoint Project Item Type"
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
ms.assetid: 18b56e7c-4efb-47a2-abfc-e9018ae38267
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# How to: Define a SharePoint Project Item Type
  사용자 지정 SharePoint 프로젝트 항목을 만들려는 경우 프로젝트 항목 형식을 정의합니다.  자세한 내용은 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)을 참조하십시오.  
  
### 프로젝트 항목 형식을 정의하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 형식을 특성 생성자에 전달합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>.  프로젝트 항목 형식 정의에서 이 특성은 새 프로젝트 항목의 문자열 식별자를 지정합니다.  *company name*.*feature name* 형식을 사용하여 모든 프로젝트 항목에 고유한 이름을 지정하는 것이 좋습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>.  이 특성은 **솔루션 탐색기**에서 이 프로젝트 항목에 대해 표시할 아이콘을 지정합니다.  이 특성은 선택 사항이므로 클래스에 적용되지 않는 경우 프로젝트 항목에 대해 기본 아이콘이 표시됩니다.  이 특성을 설정하는 경우 어셈블리에 포함된 아이콘이나 비트맵의 정규화된 이름을 전달합니다.  
  
5.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드 구현에서 *projectItemTypeDefinition* 매개 변수의 멤버를 사용하여 프로젝트 항목 형식의 동작을 정의합니다.  이 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> 인터페이스에 정의된 이벤트에 대한 액세스를 제공하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> 개체입니다.  프로젝트 항목 형식의 특정 인스턴스에 액세스하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized> 등과 같은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 이벤트를 처리합니다.  
  
## 예제  
 다음 코드 예제에서는 간단한 프로젝트 항목 형식을 정의하는 방법을 보여 줍니다.  이 프로젝트 항목 형식에서는 사용자가 프로젝트에 이 형식의 프로젝트 항목을 추가할 때 **출력** 창과 **오류 목록** 창에 메시지를 씁니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/projectitemtype.cs#2)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/projectitemtype.vb#2)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 **출력** 창과 **오류 목록** 창에 메시지를 씁니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 하려면 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다.  자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)을 참조하십시오.  
  
 프로젝트 항목을 배포하려면 어셈블리, 템플릿 및 프로젝트 항목과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)  
  
  