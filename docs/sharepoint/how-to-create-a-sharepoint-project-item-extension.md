---
title: '방법: SharePoint 프로젝트 항목 확장 만들기 | Microsoft Docs'
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
ms.openlocfilehash: 7b556bd47f35bf9c346159690925f854587e1178
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-sharepoint-project-item-extension"></a>방법: SharePoint 항목 확장명 만들기
  Visual Studio에서 이미 설치 되어 있는 SharePoint 프로젝트 항목에 기능을 추가 하려는 경우 프로젝트 항목 확장을 만듭니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)합니다.  
  
### <a name="to-create-a-project-item-extension"></a>프로젝트 항목 확장을 만들려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가 합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. 이 특성을 찾아 로드할 Visual Studio을 사용 하 여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 구현 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 형식을 특성 생성자에 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. 프로젝트 항목 확장이이 특성을 확장 하려면 프로젝트 항목을 식별 합니다. 프로젝트 항목의 ID 특성 생성자에 전달 합니다. 목록이 Visual Studio에 포함 된 프로젝트 항목의 Id에 대 한 참조 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)합니다.  
  
5.  구현에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드를 사용 하 여 멤버는 *projectItemType* 매개 변수를 확장 프로그램의 동작을 정의 합니다. 이 매개 변수는 한 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> 개체에 정의 된 이벤트에 대 한 액세스를 제공 하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> 인터페이스입니다. 특정 인스턴스를 확장 하는 프로젝트 항목 형식에 액세스 하려면 처리 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 와 같은 이벤트 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 이벤트 수신기 프로젝트 항목에 대 한 간단한 확장을 만드는 방법을 보여 줍니다. 될 때마다 이벤트 수신기 프로젝트 항목을 SharePoint 프로젝트에 추가 하는 사용자를이 확장 프로그램에 기록 메시지를는 **출력** 창 및 **오류 목록** 창.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemextension.vb#1)]  
  
 SharePoint 프로젝트 서비스를 사용 하 여 메시지를 작성 하는이 예제는 **출력** 창 및 **오류 목록** 창. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)   
 [연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  