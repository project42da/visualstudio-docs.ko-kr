---
title: "How to: Get Data for a Built-In SharePoint Node in Server Explorer"
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
ms.assetid: 86d04e0a-c114-427e-9945-da5fa339fda4
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# How to: Get Data for a Built-In SharePoint Node in Server Explorer
  **서버 탐색기**의 각 기본 제공 SharePoint 노드가 나타내는 기본 SharePoint 구성 요소에 대한 데이터를 가져올 수 있습니다.  자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 **서버 탐색기**에서 목록 노드가 나타내는 기본 SharePoint 목록에 대한 데이터를 가져오는 방법을 보여 줍니다.  기본적으로 목록 노드에는 웹 브라우저에서 목록을 열기 위해 클릭할 수 있는 **브라우저에서 보기** 상황에 맞는 메뉴 항목이 있습니다.  이 예제에서는 Visual Studio에서 목록을 직접 여는 **View in Visual Studio** 상황에 맞는 메뉴 항목을 추가하여 목록 노드를 확장합니다.  이 코드에서는 노드의 목록 데이터에 액세스하여 Visual Studio에서 열 목록의 URL을 가져옵니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorerextensionnodeinfo.cs#10)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorerextensionnodeinfo.vb#10)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 Visual Studio에서 목록을 여는 데 사용되는 <xref:EnvDTE.DTE> 개체를 가져옵니다.  SharePoint 프로젝트 서비스에 대한 자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
 SharePoint 노드의 확장을 만드는 기본 작업에 대한 자세한 내용은 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   EnvDTE  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 **서버 탐색기** 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)   
 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  