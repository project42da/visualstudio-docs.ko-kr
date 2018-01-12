---
title: "방법: SharePoint 프로젝트에 바로 가기 메뉴 항목 추가 | Microsoft Docs"
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
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c8cf3a3705fd389f16ac02d5739eeb754df99ac9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>방법: SharePoint 프로젝트에 바로 가기 메뉴 항목 추가
  모든 SharePoint 프로젝트에 바로 가기 메뉴 항목을 추가할 수 있습니다. 프로젝트 노드를 클릭할 때 메뉴 항목이 표시 **솔루션 탐색기**합니다.  
  
 다음 단계에서는 프로젝트 확장을 이미 만들었다고 가정 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)합니다.  
  
### <a name="to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>바로 가기 메뉴 항목을 SharePoint 프로젝트에 추가 하려면  
  
1.  에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 방식의 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 구현, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> 의 이벤트는 *projectService* 매개 변수입니다.  
  
2.  에 대 한 이벤트 처리기에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> 이벤트를 새 추가 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.ActionMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.AddMenuItems%2A> 이벤트 인수 매개 변수 컬렉션입니다.  
  
3.  에 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 새에 대 한 이벤트 처리기 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체, 바로 가기 메뉴 항목을 클릭할 때 실행 하려는 작업을 수행 합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서 SharePoint 프로젝트 노드의 바로 가기 메뉴 항목을 추가 하는 방법을 보여 줍니다 **솔루션 탐색기**합니다. 사용자 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 하는 경우는 **출력 창에 메시지 쓰기** 에 메시지를 표시 하는 메뉴 항목을 Visual Studio는 **출력** 창. 이 예제에서는 SharePoint 프로젝트 서비스를 사용 하 여 메시지를 표시 합니다. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
 [!code-csharp[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/CSharp/projectmenu/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/VisualBasic/projectmenu/extension/projectitemextensionmenu.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제는 클래스 라이브러리 프로젝트를 다음 어셈블리에 대 한 참조로 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 확장](../sharepoint/extending-sharepoint-projects.md)   
 [방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)  
  
  