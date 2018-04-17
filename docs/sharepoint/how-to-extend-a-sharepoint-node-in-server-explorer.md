---
title: '방법: 서버 탐색기에서 SharePoint 노드 확장 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9522e793171500b7b7f0a356eff63947fdba84cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-extend-a-sharepoint-node-in-server-explorer"></a>방법: 서버 탐색기에서 SharePoint 노드 확장
  아래에 노드를 확장할 수 있습니다는 **SharePoint 연결** 노드에서 **서버 탐색기**합니다. 기존 노드에 새 자식 노드, 바로 가기 메뉴 항목 또는 속성을 추가 하려는 경우에 유용 합니다. 자세한 내용은 참조 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)합니다.  
  
### <a name="to-extend-a-sharepoint-node-in-server-explorer"></a>서버 탐색기에서 SharePoint 노드 확장 하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  추가 <xref:System.ComponentModel.Composition.ExportAttribute> 특성을 클래스입니다. 이 특성을 찾아 로드할 Visual Studio을 사용 하 여 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 구현 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 형식을 특성 생성자에 있습니다.  
  
5.  추가 <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> 특성을 클래스입니다. 이 특성을 확장 하려면 노드 형식에 대 한 문자열 식별자를 지정 합니다.  
  
     Visual Studio에서 제공 하는 기본 제공 노드 형식을 지정 하려면 다음 열거형 값 중 하나를 특성 생성자에 전달 합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: 사용 하 여 사이트 연결 노드 (사이트 Url을 표시 하는 노드)를 지정 하는 이러한 값 사이트 노드 또는의 다른 모든 부모 노드에 **서버 탐색기**합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>: 목록, 필드 또는 콘텐츠 형식을 나타내는 노드 같은 SharePoint 사이트에서 개별 구성 요소를 나타내는 기본 제공 노드 중 하나를 지정 하려면이 값을 사용 합니다.  
  
6.  구현에서는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> 메서드를 사용 하 여 멤버는 *nodeType* 노드에 기능을 추가할 매개 변수입니다. 이 매개 변수는 한 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> 개체에 정의 된 이벤트에 대 한 액세스를 제공 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> 인터페이스입니다. 예를 들어 다음 이벤트를 처리할 수 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested>: 노드에 새 자식 노드를 추가 하려면이 이벤트를 처리 합니다. 자세한 내용은 참조 [하는 방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeMenuItemsRequested>: 노드에 사용자 지정 바로 가기 메뉴 항목을 추가 하려면이 이벤트를 처리 합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodePropertiesRequested>: 노드에 사용자 지정 속성을 추가 하려면이 이벤트를 처리 합니다. 속성에 표시 된 **속성** 노드가 선택 되었을 때 창.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 두 가지 유형의 노드 확장을 만드는 방법을 보여 줍니다.  
  
-   상황에 맞는 메뉴 항목을 SharePoint 사이트 노드를 추가 하는 확장입니다. 메뉴 항목을 클릭할 때 클릭 된 노드의 이름을 표시 합니다.  
  
-   라는 사용자 지정 속성을 추가 하는 확장 **ContosoExampleProperty** 라는 필드를 나타내는 각 노드에 **본문**합니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextension.cs#9)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextension.vb#9)]  
  
 이 확장을 노드에 편집 가능한 문자열 속성을 추가합니다. 또한 SharePoint 서버에서 읽기 전용 데이터를 표시 하는 사용자 지정 속성을 만들 수 있습니다. 이 작업을 수행 하는 방법을 보여 주는 예제를 보려면 [연습: 디스플레이 웹 파트를 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
-   System.Windows.Forms  
  
## <a name="deploying-the-extension"></a>확장 배포  
 배포 하는 **서버 탐색기** 확장을 만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 서버 탐색기에 사용자 지정 SharePoint 노드 추가](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [연습: 웹 파트를 표시 하는 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  