---
title: "방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
ms.assetid: b992a192-f926-45e6-9416-85ddfe1061d0
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7aa3ccbeaae231b0abf4885c592addc586ccfb28
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-custom-sharepoint-node-to-server-explorer"></a>방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가
  아래에 사용자 지정 노드를 추가할 수는 **SharePoint 연결** 노드에서 **서버 탐색기**합니다. 에 표시 되지 않는 추가 SharePoint 구성 요소를 표시 하려는 경우 유용 **서버 탐색기** 기본적으로 합니다. 자세한 내용은 참조 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)합니다.  
  
 사용자 지정 노드를 추가 하려면 먼저 새 노드를 정의 하는 클래스를 만듭니다. 그런 다음 기존 노드의 자식 노드를 추가 하는 확장을 만듭니다.  
  
### <a name="to-define-the-new-node"></a>새 노드를 정의 하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
    -   System.Drawing  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가 합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. 이 특성을 찾아 로드할 Visual Studio을 사용 하 여 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 구현 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 형식을 특성 생성자에 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute>. 이 특성 노드 정의에서 새 노드에 대 한 문자열 식별자를 지정합니다. 형식을 사용 하는 것이 좋습니다 *회사 이름*. *노드 이름* 모든 노드에 고유 식별자 있는지 확인 합니다.  
  
5.  구현에서는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider.InitializeType%2A> 메서드를 사용 하 여 멤버는 *typeDefinition* 매개 변수를 새 노드에의 동작을 구성 합니다. 이 매개 변수는 한 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition> 개체에 정의 된 이벤트에 대 한 액세스를 제공 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> 인터페이스입니다.  
  
     다음 코드 예제에서는 새 노드를 정의 하는 방법을 보여 줍니다. 프로젝트에 포함 리소스로 CustomChildNodeIcon 라는 아이콘이 포함 되어 있음을 전제로 합니다.  
  
     [!code-vb[SPExtensibility.ProjectSystemExtension.General#6](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#6)]
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#6](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#6)]  
  
### <a name="to-add-the-new-node-as-a-child-of-an-existing-node"></a>또한 기존 노드의 자식으로 새 노드를 추가 하려면  
  
1.  노드 정의와 동일한 프로젝트에서 구현 하는 클래스를 만들어는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스입니다.  
  
2.  추가 <xref:System.ComponentModel.Composition.ExportAttribute> 특성을 클래스입니다. 이 특성을 찾아 로드할 Visual Studio을 사용 하 여 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 구현 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 형식을 특성 생성자에 있습니다.  
  
3.  추가 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> 특성을 클래스입니다. 노드 확장에서이 특성을 확장 하려면 노드 형식에 대 한 문자열 식별자를 지정 합니다.  
  
     Visual Studio에서 제공 하는 기본 제공 노드 형식을 지정 하려면 다음 열거형 값 중 하나를 특성 생성자에 전달 합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: 사용 하 여 사이트 연결 노드 (사이트 Url을 표시 하는 노드)를 지정 하는 이러한 값 사이트 노드 또는의 다른 모든 부모 노드에 **서버 탐색기**합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>: 목록, 필드 또는 콘텐츠 형식을 나타내는 노드 같은 SharePoint 사이트에서 개별 구성 요소를 나타내는 기본 제공 노드 중 하나를 지정 하려면이 값을 사용 합니다.  
  
4.  구현에서는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> 메서드, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> 의 이벤트는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> 매개 변수입니다.  
  
5.  에 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> 이벤트 처리기의 자식 노드 컬렉션에 새 노드 추가 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeEventArgs.Node%2A> 이벤트 인수 매개 변수로 표시 되는 개체입니다.  
  
     다음 코드 예제에는 SharePoint 사이트 노드의 자식으로 새 노드를 추가 하는 방법을 보여 줍니다 **서버 탐색기**합니다.  
  
     [!code-vb[SPExtensibility.ProjectSystemExtension.General#7](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#7)]
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#7](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#7)]  
  
## <a name="complete-example"></a>완성된 예제  
 다음 코드 예제에서는 간단한 노드를 정의 하 고에서 SharePoint 사이트 노드의 자식으로 추가 하는 전체 코드를 제공 **서버 탐색기**합니다.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#5](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#5)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#5](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#5)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 프로젝트에 포함 리소스로 CustomChildNodeIcon 라는 아이콘이 포함 되어 있음을 전제로 합니다. 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
-   System.Drawing  
  
## <a name="deploying-the-extension"></a>확장 배포  
 배포 하는 **서버 탐색기** 확장을 만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [연습: 서버 탐색기를 확장하여 웹 파트 표시](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
  