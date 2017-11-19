---
title: "방법: SharePoint 프로젝트 항목 확장에 바로 가기 메뉴 항목을 추가 | Microsoft Docs"
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
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
ms.assetid: d00513a6-d66d-4fbe-9efa-ef3b08c9a73a
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7c3cb29fa90917f50b42579bf6f274aa8a20d99f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension"></a>방법: SharePoint 프로젝트 항목 확장에 바로 가기 메뉴 항목 추가
  프로젝트 항목 확장을 사용 하 여 기존 SharePoint 프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수 있습니다. 프로젝트 항목을 클릭할 때 메뉴 항목이 표시 **솔루션 탐색기**합니다.  
  
 다음 단계에서는 프로젝트 항목 확장을 이미 만들었다고 가정 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)합니다.  
  
### <a name="to-add-a-shortcut-menu-item-in-a-project-item-extension"></a>프로젝트 항목 확장에 바로 가기 메뉴 항목을 추가 하려면  
  
1.  에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 방식의 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 구현, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 의 이벤트는 *projectItemType* 매개 변수입니다.  
  
2.  에 대 한 이벤트 처리기에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트를 새 추가 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> 이벤트 인수 매개 변수 컬렉션입니다.  
  
3.  에 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 새에 대 한 이벤트 처리기 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체, 바로 가기 메뉴 항목을 클릭할 때 실행 하려는 작업을 수행 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 이벤트 수신기 프로젝트 항목에 바로 가기 메뉴 항목을 추가 하는 방법을 보여 줍니다. 프로젝트 항목을 클릭할 때 **솔루션 탐색기** 클릭는 **출력 창에 메시지 쓰기** 에 메시지를 표시 하는 메뉴 항목을 Visual Studio는 **출력**창.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionmenu.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionmenu.cs#1)]  
  
 SharePoint 프로젝트 서비스를 사용 하 여 메시지를 작성 하는이 예제는 **출력** 창. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제는 클래스 라이브러리 프로젝트를 다음 어셈블리에 대 한 참조로 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 프로젝트 항목 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [방법: SharePoint 프로젝트 항목 확장에 속성 추가](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)   
 [연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  