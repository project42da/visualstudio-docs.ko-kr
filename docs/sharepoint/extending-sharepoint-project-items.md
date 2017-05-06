---
title: "Extending SharePoint Project Items"
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
  - "project items [SharePoint development in Visual Studio], extending"
  - "SharePoint project items, extending"
  - "SharePoint development in Visual Studio, extending project items"
ms.assetid: f09f6664-196d-46d6-819f-3c6500f23536
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# Extending SharePoint Project Items
  Visual Studio에 이미 설치되어 있는 SharePoint 프로젝트 항목 형식에 기능을 추가하려는 경우 프로젝트 항목 확장을 만듭니다.  예를 들어 Visual Studio에서 기본 제공 **이벤트 수신자** 또는 **목록 정의** 프로젝트 항목에 대한 확장을 만들거나 사용자 지정 프로젝트 항목 형식에 대한 확장을 만들 수 있습니다.  모든 형식의 SharePoint 프로젝트 항목에 대한 확장을 만들 수도 있습니다.  
  
## SharePoint 프로젝트 항목을 확장하기 위한 작업  
 프로젝트 항목을 확장하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스를 구현하는 Visual Studio Extension 어셈블리를 빌드합니다.  자세한 내용은 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)을 참조하십시오.  
  
 프로젝트 항목 형식을 확장하는 경우 프로젝트 항목에 다음 기능을 추가할 수도 있습니다.  
  
-   프로젝트 항목에 바로 가기 메뉴 항목을 추가합니다.  프로젝트 항목에 대 한 바로 가기 메뉴를 열 때 메뉴 항목이 나타납니다  **솔루션 탐색기**.  이 옵션을 선택 하 고 선택 Shift \+ F10 키를 사용자나 프로젝트 항목을 마우스 오른쪽 단추로 눌러 바로 가기 메뉴를 엽니다.  자세한 내용은 [How to: Add a Shortcut Menu Item to a SharePoint Project Item Extension](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)을 참조하십시오.  
  
-   프로젝트 항목에 사용자 지정 속성을 추가합니다.  속성 표시는  **속성** 에서 프로젝트 항목을 선택 하면 창  **솔루션 탐색기**.  자세한 내용은 [How to: Add a Property to a SharePoint Project Item Extension](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)을 참조하십시오.  
  
 프로젝트 항목 확장을 만들고 배포 및 테스트하는 방법을 보여 주는 연습은 [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)을 참조하십시오.  
  
## 프로젝트 항목 형식 확장 및 프로젝트 항목 인스턴스 간 관계 이해  
 프로젝트 항목 확장을 만드는 경우 연결된 형식의 프로젝트 항목을 SharePoint 프로젝트에 추가하면 확장이 로드됩니다.  예를 들어 **이벤트 수신자** 프로젝트 항목에 대한 확장을 만드는 경우 사용자가 **이벤트 수신자** 프로젝트 항목을 프로젝트에 추가하면 확장이 로드됩니다.  연결된 프로젝트 항목 형식의 모든 인스턴스에 대해 같은 확장 인스턴스가 사용됩니다.  앞의 예제에서 사용자가 두 번째 **이벤트 수신자** 프로젝트 항목을 프로젝트에 추가하는 경우 두 번째 프로젝트 항목을 사용자 지정하는 데 같은 확장 인스턴스가 사용됩니다.  
  
 확장할 프로젝트 항목 형식의 특정 인스턴스에 액세스하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드의 구현에서 *projectItemType* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 이벤트 중 하나를 처리합니다.  예를 들어 확장할 형식의 프로젝트 항목을 프로젝트에 추가하는 시기를 결정하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 이벤트를 처리합니다.  자세한 내용은 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)을 참조하십시오.  
  
## SharePoint 프로젝트 항목의 식별자  
 각 SharePoint 프로젝트 항목에는 해당하는 문자열 식별자가 있습니다.  다음 작업을 수행하려는 경우 프로젝트 항목의 식별자를 알아야 합니다.  
  
-   프로젝트 항목의 확장을 만듭니다.  이 경우 확장할 프로젝트 항목의 식별자를 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>의 생성자에 전달해야 합니다.  모든 프로젝트 항목 형식에 대한 확장을 만들려면 **\*** 문자열 값을 전달합니다.  
  
-   프로그래밍 방식으로 프로젝트에 프로젝트 항목을 추가합니다.  이 경우 프로젝트 항목의 식별자를 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemCollection.Add%2A> 메서드에 전달해야 합니다.  
  
 다음 표에서는 Visual Studio에 포함된 SharePoint 프로젝트 항목의 식별자를 보여 줍니다.  
  
|프로젝트 항목 이름|문자열 식별자|  
|----------------|-------------|  
|비즈니스 데이터 카탈로그 모델|Microsoft.VisualStudio.SharePoint.BusinessDataConnectivity|  
|콘텐츠 형식|Microsoft.VisualStudio.SharePoint.ContentType|  
|이벤트 수신자|Microsoft.VisualStudio.SharePoint.EventHandler|  
|빈 요소|Microsoft.VisualStudio.SharePoint.GenericElement|  
|목록 정의<br /><br /> 콘텐츠 형식에서 목록 정의|Microsoft.VisualStudio.SharePoint.ListDefinition|  
|목록 인스턴스|Microsoft.VisualStudio.SharePoint.ListInstance|  
|모듈|Microsoft.VisualStudio.SharePoint.Module|  
|순차 워크플로<br /><br /> 상태 시스템 워크플로|Microsoft.VisualStudio.SharePoint.Workflow|  
|사이트 정의|Microsoft.VisualStudio.SharePoint.SiteDefinition|  
|비주얼 웹 파트|Microsoft.VisualStudio.SharePoint.VisualWebPart|  
|웹 파트|Microsoft.VisualStudio.SharePoint.WebPart|  
|워크플로 연결 폼|Microsoft.VisualStudio.SharePoint.WorkflowAssociation|  
  
## 참고 항목  
 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [How to: Add a Shortcut Menu Item to a SharePoint Project Item Extension](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [How to: Add a Property to a SharePoint Project Item Extension](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)   
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  