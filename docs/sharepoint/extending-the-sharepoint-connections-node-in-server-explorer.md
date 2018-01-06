---
title: "서버 탐색기에서 SharePoint 연결 노드 확장 | Microsoft Docs"
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
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
ms.assetid: 8bfa5950-0ef4-4417-9538-cc8a5a1c35e2
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fe9fb4a12d45cf5d713fb76fe3fe04e1346a8355
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-sharepoint-connections-node-in-server-explorer"></a>서버 탐색기에서 SharePoint 연결 노드 확장
  Visual Studio에서 연결할 수 있습니다는 개발 컴퓨터에 로컬 SharePoint 사이트를 사용 하 여는 **SharePoint 연결** 에서 노드는**서버 탐색기** 창. 이 노드는 많은 로컬 SharePoint 사이트의 구성 요소를 계층적 트리 뷰에 표시 됩니다. 예를 들어, 목록, 문서 라이브러리 및 콘텐츠 형식 로컬 사이트에서 볼 수 있습니다. 사용에 대 한 자세한 내용은 **서버 탐색기** 참조를 로컬 SharePoint 사이트에 연결 하려면 [SharePoint 연결 서버를 사용 하 여 탐색기 검색](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)합니다.  
  
 확장할 수 있습니다는 **SharePoint 연결** 노드 기존 노드에 대 한 확장 만들기 또는 사용자 지정 노드 유형을 만들고 노드의 계층 구조에 추가 합니다.  
  
## <a name="tasks-for-extending-the-sharepoint-connections-node"></a>SharePoint 연결 노드 확장에 대 한 작업  
 기존 노드를 확장 하려면 구현 하는 Visual Studio 확장을 만듭니다는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스입니다. 노드를 확장 하면 사용자 고유의 바로 가기 메뉴 항목 또는 사용자 지정 속성 같은 노드로 기능을 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)합니다.  
  
 사용자 지정 노드 유형을 만들려면 구현 하는 Visual Studio 확장을 만듭니다는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스입니다. 에 표시 되지 않는 SharePoint 사이트의 구성 요소를 표시 하려는 경우 사용자 지정 노드를 만들 **서버 탐색기** 기본적으로 합니다. 예를 들어 **서버 탐색기** 이 작업을 수행 하는 사용자 지정 노드 기본적으로 SharePoint 사이트의 웹 파트 갤러리를 추가할 수는 표시 되지 않습니다. 자세한 내용은 참조 [하는 방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md) 및 [연습: 디스플레이 웹 파트를 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다.  
  
## <a name="adding-custom-properties-to-nodes"></a>노드에 사용자 지정 속성 추가  
 노드를 확장 하거나 사용자 지정 노드 유형을 만들 때 노드에 사용자 지정 속성을 추가할 수 있습니다. 속성에 표시 된 **속성** 노드가 선택 되었을 때 창.  
  
 두 가지 유형의 노드를 추가할 수는 사용자 지정 속성에는  
  
-   SharePoint 사이트에서 읽기 전용 데이터 집합을 표시 하는 속성입니다. 데이터는 노드가 나타내는 SharePoint 구성 요소를 설명 합니다. 이 작업을 수행 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: 디스플레이 웹 파트를 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다.  
  
-   사용자 지정 읽기/쓰기 데이터를 표시 하는 속성입니다. 이 작업을 수행 하는 방법을 보여 주는 코드 예제는 참조 [하는 방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)합니다.  
  
## <a name="getting-data-for-built-in-nodes"></a>기본 제공 노드에 대 한 데이터 가져오기  
 Visual Studio에서 제공 하는 기본 제공 노드의 모든 나타내는 SharePoint 구성 요소에 대 한 일부 데이터가 들어 있습니다. 예를 들어 SharePoint 사이트의 목록을 나타내는 노드 제목 등의 기본 보기 목록에 대 한 URL 목록에 대 한 일부 데이터를 제공 합니다.  
  
 이 데이터에 액세스 하려면에서 데이터 개체를 검색 합니다.는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 의 속성은 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> 에 관심이 있는 노드를 나타내는 개체입니다. 데이터 개체의 형식은 노드 유형에 따라 다릅니다.  
  
 다음 코드 예제에서는 목록 노드에 대 한 데이터 개체를 가져오는 방법을 보여 줍니다. 이 예를 보려면이 컨텍스트에서 보다 큰 예제의 참조 하세요. [하는 방법: 서버 탐색기에서 기본 제공 SharePoint 노드에 대 한 데이터 가져오기](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)합니다.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#11)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#11)]  
  
 다음 표에서 각 기본 제공 노드 형식에 대 한 데이터 개체 유형을 나열합니다.  
  
|노드 형식|데이터 개체 유형|  
|---------------|----------------------|  
|SharePoint 사이트 노드|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerSiteNodeInfo>|  
|콘텐츠 형식|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IContentTypeNodeInfo>|  
|기능|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFeatureNodeInfo>|  
|필드|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFieldNodeInfo>|  
|목록|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListNodeInfo>|  
|목록 서식 파일|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListTemplateNodeInfo>|  
|목록 보기 (Microsoft.SharePoint.SPView)|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListViewNodeInfo>|  
|워크플로 연결|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowAssociationNodeInfo>|  
|워크플로 템플릿|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowTemplateNodeInfo>|  
  
 사용 하는 방법에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성 참조 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 웹 파트를 표시 하는 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [방법: 서버 탐색기에서 기본 제공 SharePoint 노드에 대 한 데이터 가져오기](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)   
 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [서버 탐색기를 사용 하 여 SharePoint 연결 찾아보기](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)  
  
  