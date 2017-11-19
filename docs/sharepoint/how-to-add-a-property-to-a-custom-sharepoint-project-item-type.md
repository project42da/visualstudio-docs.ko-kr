---
title: "방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가 | Microsoft Docs"
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
ms.assetid: 47e940f6-1779-4530-aea6-c43a370c544f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4c8971d6da08afa6140c049aa81937b0804cd363
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-property-to-a-custom-sharepoint-project-item-type"></a>방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의한 경우에 프로젝트 항목에 속성을 추가할 수 있습니다. 에 해당 속성이 표시는 **속성** 창에서 프로젝트 항목을 선택 하는 경우 **솔루션 탐색기**합니다.  
  
 다음 단계에서는 SharePoint 프로젝트 항목 형식 사용자 고유의 이미 정의한 가정 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)합니다.  
  
### <a name="to-add-a-property-to-a-definition-of-a-project-item-type"></a>프로젝트 항목 형식 정의에 속성을 추가 하려면  
  
1.  사용자 지정 프로젝트 항목 형식에 추가 하는 속성을 나타내는 가능한 공용 속성을 사용 하는 클래스를 정의 합니다. 사용자 지정 프로젝트 항목 형식에 여러 속성을 추가 하려는 경우 동일한 클래스 또는 다른 클래스에서 모든 속성을 정의할 수 있습니다.  
  
2.  에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 방식의 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 의 이벤트는 *projectItemTypeDefinition* 매개 변수입니다.  
  
3.  에 대 한 이벤트 처리기에는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 이벤트를 사용자 지정 속성 클래스의 인스턴스를 추가 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> 이벤트 인수 매개 변수 컬렉션입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 라는 속성을 추가 하는 방법을 보여 줍니다. **예제 속성** 을 사용자 지정 프로젝트 항목 형식입니다.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#11)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#11)]  
  
### <a name="understanding-the-code"></a>코드 이해  
 동일한 인스턴스에 충족 되도록는 `CustomProperties` 클래스 될 때마다 사용 됩니다는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 이벤트의 발생에 대 한 속성 개체를 저장 하는 코드 예제는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 이 이벤트가 발생 하는 시점에 프로젝트 첫 번째 항목의 속성입니다. 코드는이 이벤트가 다시 발생할 때마다이 개체를 검색 합니다. 사용 하는 방법에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 프로젝트 항목으로 데이터를 저장 하는 속성 참조 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)합니다.  
  
 속성 값에 변경 내용을 유지는 **설정** 에 대 한 접근자 `ExampleProperty` 에 새 값을 저장는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성의는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 속성이 연결 된 개체입니다. 사용 하는 방법에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 프로젝트 항목을 사용 하 여 데이터를 유지 하는 속성 참조 [SharePoint 프로젝트 시스템의 확장에 대 한 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)합니다.  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>사용자 지정 속성의 동작 지정  
 사용자 지정 속성 나타나고에서 동작을 정의할 수 있습니다는 **속성** 창에서 특성을 적용 하 여는 <xref:System.ComponentModel> 속성 정의에 네임 스페이스입니다. 다음 특성은 많은 시나리오에서 유용 합니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>:에 표시 되는 속성의 이름을 지정 합니다.는 **속성** 창.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>:의 맨 아래에 표시 되는 설명 문자열을 지정 합니다.는 **속성** 창에서 속성을 선택 합니다.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: 속성의 기본값을 지정합니다.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: 사용자 지정에 표시 되는 문자열 간의 변환을 지정는 **속성** 창과 문자열이 아닌 속성 값입니다.  
  
-   <xref:System.ComponentModel.EditorAttribute>: 속성을 수정 하는 데 사용자 지정 편집기를 지정 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이러한 코드 예제는 클래스 라이브러리 프로젝트에 다음 어셈블리에 대 한 참조로 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
 프로젝트 항목을 배포 하려면 만들기를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리, 서식 파일 및 프로젝트 항목과 함께 배포 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  