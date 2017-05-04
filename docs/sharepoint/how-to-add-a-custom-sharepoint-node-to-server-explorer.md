---
title: "How to: Add a Custom SharePoint Node to Server Explorer | Microsoft Docs"
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
  - "SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer"
  - "SharePoint Connections [SharePoint development in Visual Studio], creating a new node type"
ms.assetid: b992a192-f926-45e6-9416-85ddfe1061d0
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# How to: Add a Custom SharePoint Node to Server Explorer
  **서버 탐색기**의 **SharePoint 연결** 노드 아래에 사용자 지정 노드를 추가할 수 있습니다.  이 기능은 기본적으로 **서버 탐색기**에 표시되지 않는 추가 SharePoint 구성 요소를 표시하려는 경우에 유용합니다.  자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
 사용자 지정 노드를 추가하려면 먼저 새 노드를 정의하는 클래스를 만듭니다.  그런 다음 기존 노드의 자식으로 이 노드를 추가하는 확장을 만듭니다.  
  
### 새 노드를 정의하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
    -   System.Drawing  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 형식을 특성 생성자에 전달합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute>.  노드 정의에서 이 특성은 새 노드의 문자열 식별자를 지정합니다.  *company name*.*node name* 형식을 사용하여 모든 노드에 고유한 식별자를 지정하는 것이 좋습니다.  
  
5.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider.InitializeType%2A> 메서드 구현에서 *typeDefinition* 매개 변수의 멤버를 사용하여 새 노드의 동작을 구성합니다.  이 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> 인터페이스에 정의된 이벤트에 대한 액세스를 제공하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition> 개체입니다.  
  
     다음 코드 예제에서는 새 노드를 정의하는 방법을 보여 줍니다.  이 예제에서는 CustomChildNodeIcon이라는 아이콘이 포함 리소스로 프로젝트에 포함되어 있다고 가정합니다.  
  
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorernode.cs#6)]
     [!code-vb[SPExtensibility.ProjectSystemExtension.General#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorernode.vb#6)]  
  
### 기존 노드의 자식으로 새 노드를 추가하려면  
  
1.  노드 정의와 동일한 프로젝트에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
2.  클래스에 <xref:System.ComponentModel.Composition.ExportAttribute> 특성을 추가합니다.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 형식을 특성 생성자에 전달합니다.  
  
3.  클래스에 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> 특성을 추가합니다.  노드 확장에서 이 특성은 확장할 노드의 형식을 나타내는 문자열 식별자를 지정합니다.  
  
     Visual Studio에서 제공되는 기본 제공 노드 형식을 지정하려면 다음 열거형 값 중 하나를 특성 생성자에 전달합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: 사이트 연결 노드\(사이트 URL을 표시하는 노드\), 사이트 노드 또는 다른 모든 부모 노드를 지정하려면 **서버 탐색기**에서 이러한 값을 사용합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>. SharePoint 사이트의 개별 구성 요소를 나타내는 기본 제공 노드, 즉 목록, 필드 또는 콘텐츠 형식을 나타내는 노드 중 하나를 지정하려면 이러한 값을 사용합니다.  
  
4.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> 메서드의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> 이벤트를 처리합니다.  
  
5.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> 이벤트 처리기에서 이벤트 인수 매개 변수를 통해 노출되는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeEventArgs.Node%2A> 개체의 자식 노드 컬렉션에 새 노드를 추가합니다.  
  
     다음 코드 예제에서는 새 노드를 추가하고 **서버 탐색기**에 SharePoint 사이트 노드의 자식으로 이 노드를 추가하는 방법을 보여 줍니다.  
  
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#7](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorernode.cs#7)]
     [!code-vb[SPExtensibility.ProjectSystemExtension.General#7](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorernode.vb#7)]  
  
## 완성된 예제  
 다음 코드 예제에서는 간단한 노드를 정의하고 **서버 탐색기**에 SharePoint 사이트 노드의 자식으로 이를 추가하는 코드 전체를 보여 줍니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#5](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorernode.cs#5)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#5](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorernode.vb#5)]  
  
## 코드 컴파일  
 이 예제에서는 CustomChildNodeIcon이라는 아이콘이 포함 리소스로 프로젝트에 포함되어 있다고 가정합니다.  또한 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
-   System.Drawing  
  
## 확장 배포  
 **서버 탐색기** 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
  