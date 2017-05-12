---
title: "How to: Extend a SharePoint Node in Server Explorer"
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
ms.assetid: 5e443950-12e6-40d1-864b-c384b6be4ce4
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# How to: Extend a SharePoint Node in Server Explorer
  **서버 탐색기**의 **SharePoint 연결** 노드 아래에 있는 노드를 확장할 수 있습니다.  이렇게 하면 새 자식 노드, 바로 가기 메뉴 항목 또는 속성을 기존 노드에 추가하려는 경우에 유용합니다.  자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
### 서버 탐색기에서 SharePoint 노드를 확장하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 <xref:System.ComponentModel.Composition.ExportAttribute> 특성을 추가합니다.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 형식을 특성 생성자에 전달합니다.  
  
5.  클래스에 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> 특성을 추가합니다.  이 특성은 확장할 노드의 형식을 나타내는 문자열 식별자를 지정합니다.  
  
     Visual Studio에서 제공되는 기본 제공 노드 형식을 지정하려면 다음 열거형 값 중 하나를 특성 생성자에 전달합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: 사이트 연결 노드\(사이트 URL을 표시하는 노드\), 사이트 노드 또는 다른 모든 부모 노드를 지정하려면 **서버 탐색기**에서 이러한 값을 사용합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>. SharePoint 사이트의 개별 구성 요소를 나타내는 기본 제공 노드, 즉 목록, 필드 또는 콘텐츠 형식을 나타내는 노드 중 하나를 지정하려면 이러한 값을 사용합니다.  
  
6.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> 메서드 구현에서 *nodeType* 매개 변수의 멤버를 사용하여 노드에 기능을 추가합니다.  이 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> 인터페이스에 정의된 이벤트에 대한 액세스를 제공하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> 개체입니다.  예를 들어, 다음과 같은 이벤트를 처리할 수 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested>. 새 자식 노드를 노드에 추가하려면 이 이벤트를 처리합니다.  자세한 내용은 [How to: Add a Custom SharePoint Node to Server Explorer](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)를 참조하십시오.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeMenuItemsRequested>. 사용자 지정 바로 가기 메뉴 항목을 노드에 추가하려면 이 이벤트를 처리합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodePropertiesRequested>. 사용자 지정 속성을 노드에 추가하려면 이 이벤트를 처리합니다.  속성은 노드를 선택하면 **속성** 창에 표시됩니다.  
  
## 예제  
 다음 코드 예제에서는 두 가지 다른 유형의 노드 확장을 만드는 방법을 보여 줍니다.  
  
-   상황에 맞는 메뉴 항목을 SharePoint 사이트 노드에 추가하는 확장.  메뉴 항목을 클릭하면 클릭한 노드의 이름이 표시됩니다.  
  
-   **Body**라는 필드를 나타내는 각 노드에 **ContosoExampleProperty**라는 사용자 지정 속성을 추가하는 확장  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#9](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/serverexplorerextension.cs#9)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#9](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/serverexplorerextension.vb#9)]  
  
 이 확장은 편집 가능한 문자열 속성을 노드에 추가합니다.  또한 SharePoint 서버의 읽기 전용 데이터를 표시하는 사용자 지정 속성을 만들 수도 있습니다.  이 작업을 수행하는 방법을 보여 주는 예제를 보려면 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
-   System.Windows.Forms  
  
## 확장 배포  
 **서버 탐색기** 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [How to: Add a Custom SharePoint Node to Server Explorer](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  