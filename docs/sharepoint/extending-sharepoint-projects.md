---
title: SharePoint 프로젝트 확장 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ab99253efbef61a3a041f261e44e8944bc7d6024
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764155"
---
# <a name="extend-sharepoint-projects"></a>SharePoint 프로젝트 확장
  SharePoint 프로젝트의 프로젝트 수준 기능을 사용자 지정 하려는 경우 프로젝트 확장을 만듭니다. 예를 들어 사용자 지정 프로젝트 속성을 추가 하거나 Visual Studio에서 SharePoint 솔루션을 개발 하는 사용자 때 발생 하는 프로젝트 수준 이벤트에 응답할 수 있습니다.  
  
## <a name="create-project-extensions"></a>프로젝트 확장명 만들기
 프로젝트 항목을 확장 하려면 구현 하는 Visual Studio 확장 어셈블리를 빌드하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스입니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)합니다.  
  
 프로젝트 확장을 만들 때 SharePoint 프로젝트에 다음 기능을 추가할 수도 있습니다.  
  
-   바로 가기 메뉴 항목을 추가 합니다. 메뉴 항목에서 SharePoint 프로젝트 노드에 대 한 바로 가기 메뉴를 열 때 나타납니다 **솔루션 탐색기** 선택 하 여 노드를 마우스 오른쪽 단추로 클릭 하거나 선택 된 **Shift** +  **F10** 키입니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)합니다.  
  
-   사용자 지정 속성을 추가 합니다. 에 해당 속성이 표시는 **속성** 창에서 SharePoint 프로젝트를 선택 하면 **솔루션 탐색기**합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)합니다.  
  
 만들기, 배포 및 프로젝트 확장을 테스트 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: SharePoint 프로젝트 확장 만들기](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)합니다.  
  
## <a name="understand-the-relationship-between-project-extensions-and-project-instances"></a>확장 프로젝트 및 프로젝트 인스턴스 간의 관계를 이해
 확장에서 모든 종류의 SharePoint 프로젝트를 열면 프로젝트 확장을 만드는 경우 로드 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 목록 정의 콘텐츠 형식 및 이벤트 수신기 등 몇 개의 SharePoint 프로젝트 템플릿이 포함 되어 있습니다. 그러나 SharePoint 프로젝트 유형이 하나만 있습니다. 에 표시 되는 프로젝트 유형에 **새 프로젝트** 대화 상자에는 하나 이상의 SharePoint 프로젝트 항목을 묶어 템플릿만 됩니다. 하나의 SharePoint 프로젝트 형식 이므로 확장 하나의 프로젝트에 대해 만든 모든 SharePoint 프로젝트에 적용 됩니다. 예를 들어에 적용 되는 확장을 만들 수는 없습니다는 **콘텐츠 형식** 프로젝트.  
  
 인스턴스를 특정 프로젝트에 액세스 하려면 처리 중 하나는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> 의 이벤트는 *projectService* 구현에서 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 메서드. 예를 들어 SharePoint 프로젝트는 솔루션에 추가 된 경우를 확인 하려면 처리는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> 이벤트입니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)합니다.  
  
## <a name="see-also"></a>참고자료
 [방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [방법: SharePoint 프로젝트에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [연습: SharePoint 프로젝트 확장 만들기](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)   
 [확장 SharePoint 패키징 및 배포](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
