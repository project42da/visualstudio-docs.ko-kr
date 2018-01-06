---
title: "방법: SharePoint 프로젝트 항목 형식 정의 | Microsoft Docs"
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
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: 18b56e7c-4efb-47a2-abfc-e9018ae38267
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fb19c360f19890c7e9c116ad721dd99ef633d47a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-sharepoint-project-item-type"></a>방법: SharePoint 프로젝트 항목 형식 정의
  사용자 지정 SharePoint 프로젝트 항목을 만들 때 프로젝트 항목 형식을 정의 합니다. 자세한 내용은 참조 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)합니다.  
  
### <a name="to-define-a-project-item-type"></a>프로젝트 항목 형식 정의 하려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가 합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. 이 특성을 찾아 로드할 Visual Studio을 사용 하 여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 형식을 특성 생성자에 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. 이 특성 프로젝트 항목 형식 정의에서 새 프로젝트 항목에 대 한 문자열 식별자를 지정합니다. 형식을 사용 하는 것이 좋습니다 *회사 이름*. *기능 이름* 모든 프로젝트 항목 고유 이름을 갖도록 할 수 있도록 합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>. 이 특성은이 프로젝트 항목에 대해 표시할 아이콘을 지정 **솔루션 탐색기**합니다. 이 특성은 선택 사항입니다. 클래스에 적용 되지 않은 경우 Visual Studio 프로젝트 항목에 대 한 기본 아이콘을 표시 합니다. 아이콘 또는 비트맵은 어셈블리에 포함 된의 정규화 된 이름을 전달 하는 경우이 특성을 설정 합니다.  
  
5.  구현에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드를 사용 하 여 멤버는 *projectItemTypeDefinition* 매개 변수는 프로젝트 항목 형식의 동작을 정의 합니다. 이 매개 변수는 한 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> 개체에 정의 된 이벤트에 대 한 액세스를 제공 하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> 인터페이스입니다. 특정 인스턴스의 프로젝트 항목 형식에 액세스 하려면 처리 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 와 같은 이벤트 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 간단한 프로젝트 항목 형식을 정의 하는 방법을 보여 줍니다. 이 프로젝트 항목 형식에 메시지를 씁니다는 **출력** 창 및 **오류 목록** 창 사용자는 이러한 종류의 프로젝트 항목을 프로젝트에 추가 합니다.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemtype.vb#2)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemtype.cs#2)]  
  
 SharePoint 프로젝트 서비스를 사용 하 여 메시지를 작성 하는이 예제는 **출력** 창 및 **오류 목록** 창. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
 프로젝트 항목을 배포 하려면 만들기를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리, 서식 파일 및 프로젝트 항목과 함께 배포 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [연습: 항목 템플릿, 1 부와 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)  
  
  