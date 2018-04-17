---
title: SharePoint 프로젝트 항목 확장 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1cc202b2e3e303f8f6e92b82bbfbc6f5525966bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="extending-sharepoint-project-items"></a>SharePoint 프로젝트 항목 확장
  Visual Studio에서 이미 설치 되어 있는 SharePoint 프로젝트 항목의 형식에 기능을 추가 하려는 경우 프로젝트 항목 확장을 만듭니다. 예를 들어 기본 제공에 대 한 확장을 만들 수 있습니다 **이벤트 수신기** 또는 **목록 정의** Visual Studio에서 프로젝트 항목 또는 사용자 지정 프로젝트 항목 형식에 대 한 확장을 만들 수 있습니다. 모든 SharePoint 프로젝트 항목 형식에 대 한 확장을 만들 수도 있습니다.  
  
## <a name="tasks-for-extending-sharepoint-project-items"></a>SharePoint 프로젝트 항목 확장에 대 한 작업  
 프로젝트 항목을 확장 하려면 구현 하는 Visual Studio 확장 어셈블리를 빌드하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스입니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)합니다.  
  
 프로젝트 항목을 확장 하는 경우 프로젝트 항목에도 다음과 같은 기능을 추가할 수 있습니다.  
  
-   프로젝트 항목에 바로 가기 메뉴 항목을 추가 합니다. 메뉴 항목에서 프로젝트 항목에 대 한 바로 가기 메뉴를 열 때 나타납니다 **솔루션 탐색기**합니다. 프로젝트 항목을 마우스 오른쪽 단추로 클릭 하 여 바로 가기 메뉴를 열고 하거나 키를 선택한 다음 Shift + f 10을 선택 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 확장에 바로 가기 메뉴 항목을 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)합니다.  
  
-   프로젝트 항목에 사용자 지정 속성을 추가 합니다. 에 해당 속성이 표시는 **속성** 창에서 프로젝트 항목을 선택 하면 **솔루션 탐색기**합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 확장에 속성 추가](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)합니다.  
  
 만들기, 배포 및 프로젝트 항목 확장을 테스트 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)합니다.  
  
## <a name="understanding-the-relationship-between-project-item-extensions-and-project-item-instances"></a>프로젝트 항목 확장 프로그램 및 프로젝트 항목 인스턴스 간 관계 이해  
 프로젝트 항목 확장을 만들 때 연결 된 형식의 프로젝트 항목을 SharePoint 프로젝트에 추가 될 때 Visual Studio 확장을 로드 합니다. 예를 들어 확장을 만드는 경우 **이벤트 수신기** 프로젝트 항목, Visual Studio 확장 프로그램 사용자에 추가 로드는 **이벤트 수신기** 프로젝트에 프로젝트 항목입니다. Visual Studio 관련된 프로젝트 항목 형식의 모든 인스턴스에 대 한 확장 프로그램의 같은 인스턴스를 사용합니다. 이전 예제에서 사용자는 두 번째 추가 **이벤트 수신기** 프로젝트에 프로젝트 항목, 확장 프로그램의 같은 인스턴스는 두 번째 프로젝트 항목을 사용자 지정 하는 데 사용 됩니다.  
  
 특정 인스턴스를 확장 하는 프로젝트 항목 형식에 액세스 하려면 처리 중 하나는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 의 이벤트는 *projectItemType* 구현에서 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드. 예를 들어 프로젝트에 확장 하는 형식의 프로젝트 항목을 추가 하는 경우를 확인 하려면 처리는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 이벤트입니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)합니다.  
  
## <a name="identifiers-for-sharepoint-project-items"></a>SharePoint 프로젝트 항목에 대 한 식별자  
 각 SharePoint 프로젝트 항목에 해당 하는 문자열 식별자입니다. 다음 작업을 수행 하려는 경우 프로젝트 항목에 대 한 식별자를 알고 있어야 합니다.  
  
-   프로젝트 항목에 대 한 확장을 만듭니다. 생성자에 게 확장 하려는 경우 프로젝트 항목에 대 한 식별자를 전달 해야 하는 경우에 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>합니다. 모든 프로젝트 항목 형식에 대 한 확장을 생성, 전달 된 **\*** 문자열 값입니다.  
  
-   프로그래밍 방식으로 프로젝트에 프로젝트 항목을 추가 합니다. 프로젝트 항목에 대 한 식별자를 전달 해야 하는 경우에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemCollection.Add%2A> 메서드.  
  
 다음 표에서 Visual Studio에 포함 되어 있는 SharePoint 프로젝트 항목에 대 한 식별자를 나열 합니다.  
  
|프로젝트 항목 이름|문자열 식별자|  
|-----------------------|-----------------------|  
|비즈니스 데이터 카탈로그 모델|Microsoft.VisualStudio.SharePoint.BusinessDataConnectivity|  
|콘텐츠 형식|Microsoft.VisualStudio.SharePoint.ContentType|  
|이벤트 수신기|Microsoft.VisualStudio.SharePoint.EventHandler|  
|빈 요소|Microsoft.VisualStudio.SharePoint.GenericElement|  
|목록 정의<br /><br /> 콘텐츠 형식에서 목록 정의|Microsoft.VisualStudio.SharePoint.ListDefinition|  
|목록 인스턴스|Microsoft.VisualStudio.SharePoint.ListInstance|  
|Module|Microsoft.VisualStudio.SharePoint.Module|  
|순차적 워크플로<br /><br /> 정적 컴퓨터 워크플로|Microsoft.VisualStudio.SharePoint.Workflow|  
|사이트 정의|Microsoft.VisualStudio.SharePoint.SiteDefinition|  
|비주얼 웹 파트|Microsoft.VisualStudio.SharePoint.VisualWebPart|  
|웹 파트|Microsoft.VisualStudio.SharePoint.WebPart|  
|워크플로 연결 양식|Microsoft.VisualStudio.SharePoint.WorkflowAssociation|  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 프로젝트 항목 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [방법: SharePoint 프로젝트 항목 확장에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [방법: SharePoint 프로젝트 항목 확장에 속성 추가](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)   
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)  
  