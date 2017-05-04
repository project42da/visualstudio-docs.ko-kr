---
title: "Extending the SharePoint Connections Node in Server Explorer | Microsoft Docs"
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
  - "SharePoint Connections [SharePoint development in Visual Studio], extending a node"
  - "SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer"
  - "SharePoint Connections [SharePoint development in Visual Studio], creating a new node type"
ms.assetid: 8bfa5950-0ef4-4417-9538-cc8a5a1c35e2
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# Extending the SharePoint Connections Node in Server Explorer
  Visual Studio에서는 개발 컴퓨터에 있는 로컬 SharePoint 사이트에연결하다을 사용 하 여 수는  **SharePoint 연결** 에서 노드는**서버 탐색기**창.   이 노드에는 로컬 SharePoint 사이트의 많은 구성 요소가 계층 트리 뷰로 표시됩니다.  예를 들어 로컬 사이트의 목록, 문서 라이브러리 및 콘텐츠 형식을 볼 수 있습니다. **서버 탐색기**를 사용하여 로컬 SharePoint 사이트에 연결하는 방법에 대한 자세한 내용은 [서버 탐색기를 사용하여 SharePoint 연결 찾아보기](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)를 참조하십시오.  
  
 기존 노드에 대한 확장을 만들거나, 사용자 지정 노드 형식을 만들고 이를 노드 계층 구조에 추가하여 **SharePoint 연결** 노드를 확장할 수 있습니다.  
  
## SharePoint 연결 노드 확장 작업  
 기존 노드를 확장하려면 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현하는 Visual Studio 확장을 만듭니다.  노드를 확장하면 고유한 바로 가기 메뉴 항목이나 사용자 지정 속성 등과 같은 기능을 노드에 추가할 수 있습니다.  자세한 내용은 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하십시오.  
  
 사용자 지정 노드 형식을 만들려면 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스를 구현하는 Visual Studio 확장을 만듭니다.  기본적으로 **서버 탐색기**에 표시되지 않는 SharePoint 사이트의 구성 요소를 표시하려는 경우 사용자 지정 노드를 만듭니다.  예를 들어 SharePoint 사이트의 웹 파트 갤러리는 기본적으로 **서버 탐색기**에 표시되지 않지만 이 작업을 수행하는 사용자 지정 노드를 추가할 수 있습니다.  자세한 내용은 [How to: Add a Custom SharePoint Node to Server Explorer](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md) 및 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)를 참조하십시오.  
  
## 노드에 사용자 지정 속성 추가  
 노드를 확장하거나 사용자 지정 노드 형식을 만들면 노드에 사용자 지정 속성을 추가할 수 있습니다.  속성은 노드를 선택하면 **속성** 창에 표시됩니다.  
  
 노드에 추가할 수 있는 사용자 지정 속성에는 두 가지 형식이 있습니다.  
  
-   SharePoint 사이트의 읽기 전용 데이터 집합을 표시하는 속성.  데이터는 노드에서 나타내는 SharePoint 구성 요소를 설명합니다.  이 작업을 수행하는 방법을 보여 주는 연습은 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)를 참조하십시오.  
  
-   사용자 지정 읽기\/쓰기 데이터를 표시하는 속성.  이 작업을 수행하는 방법을 보여 주는 코드 예제를 보려면 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하십시오.  
  
## 기본 제공 노드의 데이터 가져오기  
 Visual Studio의 모든 기본 제공 노드에는 해당 노드가 나타내는 SharePoint 구성 요소에 대한 몇 가지 데이터가 포함됩니다.  예를 들어 SharePoint 사이트의 목록을 나타내는 노드에서는 목록에 대한 기본 뷰의 URL, 제목 등과 같은 목록에 대한 몇 가지 데이터를 제공합니다.  
  
 이 데이터에 액세스하려면 필요한 노드를 나타내는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> 개체의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성에서 데이터 개체를 검색합니다.  데이터 개체의 형식은 노드의 형식에 따라 다릅니다.  
  
 다음 코드 예제에서는 목록 노드의 데이터 개체를 가져오는 방법을 보여 줍니다.  더 큰 컨텍스트에서 이 예제를 보려면 [How to: Get Data for a Built-In SharePoint Node in Server Explorer](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)를 참조하십시오.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#11](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorerextensionnodeinfo.cs#11)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#11](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorerextensionnodeinfo.vb#11)]  
  
 다음 표에는 각 기본 제공 노드 형식에 대한 데이터 개체 형식이 나와 있습니다.  
  
|노드 형식|데이터 개체 형식|  
|-----------|---------------|  
|SharePoint 사이트 노드|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerSiteNodeInfo>|  
|콘텐츠 형식|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IContentTypeNodeInfo>|  
|기능|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFeatureNodeInfo>|  
|필드|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFieldNodeInfo>|  
|List|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListNodeInfo>|  
|목록 템플릿|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListTemplateNodeInfo>|  
|목록 뷰\(Microsoft.SharePoint.SPView\)|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListViewNodeInfo>|  
|워크플로 연결|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowAssociationNodeInfo>|  
|워크플로 템플릿|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowTemplateNodeInfo>|  
  
 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성을 사용하는 방법에 대한 자세한 내용은 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)을 참조하십시오.  
  
## 참고 항목  
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [How to: Add a Custom SharePoint Node to Server Explorer](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [How to: Get Data for a Built-In SharePoint Node in Server Explorer](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)   
 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [서버 탐색기를 사용하여 SharePoint 연결 찾아보기](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)  
  
  