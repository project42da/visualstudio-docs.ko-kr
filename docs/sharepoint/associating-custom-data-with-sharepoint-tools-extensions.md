---
title: "Associating Custom Data with SharePoint Tools Extensions"
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
  - "projects [SharePoint development in Visual Studio], associating custom data"
  - "project items [SharePoint development in Visual Studio], associating custom data"
  - "SharePoint project items, associating custom data"
  - "SharePoint projects, associating custom data"
  - "SharePoint development in Visual Studio, extensibility features"
ms.assetid: cfc87272-85a1-4c36-89e4-2662417d59ea
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# Associating Custom Data with SharePoint Tools Extensions
  SharePoint 도구 확장에서 특정 개체에 사용자 지정 데이터를 추가할 수 있습니다.  이러한 연결은 확장의 한 부분에 데이터가 있고 나중에 확장의 다른 코드에서 이 데이터에 액세스하려는 경우에 유용합니다.  데이터를 저장하고 액세스하기 위해 사용자 지정된 방식을 구현하는 대신 확장에서 데이터를 개체와 연결한 다음 나중에 동일한 개체에서 데이터를 검색할 수 있습니다.  
  
 Visual Studio에서 특정 항목과 관련된 데이터를 유지하려는 경우에도 사용자 지정 데이터를 개체에 추가하는 것이 유용합니다.  SharePoint 도구 확장은 Visual Studio에서 한 번만 로드되므로 확장은 항상 서로 다른 여러 항목\(예: 프로젝트, 프로젝트 항목 또는 **Server Explorer** 노드\)과 함께 작동할 수도 있습니다.  특정 항목에만 관련된 사용자 지정 데이터가 있는 경우 해당 항목을 나타내는 개체에 데이터를 추가할 수 있습니다.  
  
 SharePoint 도구 확장의 개체에 사용자 지정 데이터를 추가하는 경우 추가한 데이터가 유지되지 않습니다.  추가한 데이터는 개체의 수명 동안에만 사용할 수 있습니다.  가비지 수집에서 개체를 회수하면 이 데이터가 손실됩니다.  
  
 SharePoint 프로젝트 시스템의 확장에서는 확장이 언로드된 후 유지되는 문자열 데이터를 저장할 수도 있습니다.  자세한 내용은 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)을 참조하십시오.  
  
## 사용자 지정 데이터를 포함할 수 있는 개체  
 사용자 지정 데이터는 SharePoint 도구 개체 모델에서 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> 인터페이스를 구현하는 모든 개체에 추가할 수 있습니다.  이 인터페이스는 사용자 지정 데이터 개체의 컬렉션인 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성 하나만 정의합니다.  다음 형식은 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject>를 구현합니다.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMappedFolder>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMenuItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectMember>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentContext>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition>  
  
## 사용자 지정 데이터 추가 및 검색  
 SharePoint 도구 확장의 개체에 사용자 지정 데이터를 추가하려면 데이터를 추가할 개체의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성을 가져온 다음 <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.Add%2A> 메서드를 사용하여 개체에 데이터를 추가합니다.  
  
 SharePoint 도구 확장에서 개체의 사용자 지정 데이터를 검색하려면 개체의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성을 가져온 후 다음 메서드 중 하나를 사용합니다.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.TryGetValue%2A>.  이 메서드에서는 데이터 개체가 있으면 **true**를 반환하고, 그렇지 않으면 **false**를 반환합니다.  이 메서드를 사용하여 값 형식 또는 참조 형식의 인스턴스를 검색할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.GetValue%2A>.  이 메서드에서는 데이터 개체가 있으면 데이터 개체를 반환하고 그렇지 않으면 **null**을 반환합니다.  이 메서드로는 참조 형식의 인스턴스만 검색할 수 있습니다.  
  
 다음 코드 예제에서는 특정 데이터 개체가 프로젝트 항목에 이미 연결되어 있는지 여부를 확인합니다.  데이터 개체가 이미 프로젝트 항목과 연결되어 있으면 코드에서는 프로젝트 항목의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성에 해당 개체를 추가합니다.  보다 큰 예제의 컨텍스트에서 이 예제를 보려면 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)를 참조하십시오.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/cs/extension/projectitemtypeproperty.cs#13)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/vb/extension/projectitemtypeproperty.vb#13)]  
  
## 참고 항목  
 [Programming Concepts and Features for SharePoint Tools Extensions](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)  
  
  