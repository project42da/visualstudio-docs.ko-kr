---
title: "방법: 서버 탐색기에서 기본 제공 SharePoint 노드에 대 한 데이터 가져오기 | Microsoft Docs"
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
ms.assetid: 86d04e0a-c114-427e-9945-da5fa339fda4
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b61003516d7551c99f6e265ca2eeced9226958df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>방법: 서버 탐색기에서 기본 제공 SharePoint 노드에 대한 데이터 가져오기
  각 기본 제공 SharePoint 노드에 대해 **서버 탐색기**, 노드를 나타내는 기본 SharePoint 구성 요소에 대 한 데이터를 가져올 수 있습니다. 자세한 내용은 참조 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에는 목록 노드를 표시 하는 기본 SharePoint 목록에 대 한 데이터를 가져오는 방법을 보여 줍니다 **서버 탐색기**합니다. 기본적으로 목록 노드에 적용 한 **브라우저에서 보기** 웹 브라우저에서 목록을 열기 위해 클릭할 수 있는 상황에 맞는 메뉴 항목입니다. 추가 하 여 목록 노드를 확장 하는이 예제는 **Visual Studio에서 보기** Visual Studio에서 직접 목록을 상황에 맞는 메뉴 항목입니다. Visual Studio에서 열 목록의 URL을 가져올 노드에 대 한 목록 데이터를 액세스 하는 코드입니다.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]  
  
 SharePoint 프로젝트 서비스를 사용 하 여 가져올 수는이 예제는 <xref:EnvDTE.DTE> Visual Studio에서 열려는 사용 되는 개체를 나열 합니다. SharePoint 프로젝트 서비스에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
 SharePoint 노드에 대 한 확장 프로그램을 만들려면 기본 작업에 대 한 자세한 내용은 참조 [하는 방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   EnvDTE  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 배포 하는 **서버 탐색기** 확장을 만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [방법: 서버 탐색기에서 SharePoint 노드 확장](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [SharePoint 프로젝트 서비스 사용](../sharepoint/using-the-sharepoint-project-service.md)   
 [Visual Studio에서 SharePoint 도구에 대한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  