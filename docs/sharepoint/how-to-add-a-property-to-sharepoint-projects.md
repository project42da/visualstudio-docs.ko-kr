---
title: "방법: SharePoint 프로젝트에 속성 추가 | Microsoft Docs"
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
ms.assetid: c5eb4900-c35f-490a-b856-bf167da2d293
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 290f5d4b3632d5c3ee40e7171aa4a0ed967004dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-property-to-sharepoint-projects"></a>방법: SharePoint 프로젝트에 속성 추가
  모든 SharePoint 프로젝트에 속성을 추가 하려면 프로젝트 확장을 사용할 수 있습니다. 에 해당 속성이 표시는 **속성** 창에서 프로젝트를 선택한 경우 **솔루션 탐색기**합니다.  
  
 다음 단계에서는 프로젝트 확장을 이미 만들었다고 가정 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)합니다.  
  
### <a name="to-add-a-property-to-a-sharepoint-project"></a>SharePoint 프로젝트에 속성을 추가 하려면  
  
1.  SharePoint 프로젝트에 추가 하는 속성을 나타내는 가능한 공용 속성을 사용 하는 클래스를 정의 합니다. 여러 속성을 추가 하려는 경우 동일한 클래스 또는 다른 클래스에서 모든 속성을 정의할 수 있습니다.  
  
2.  에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 방식의 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 구현, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> 의 이벤트는 *projectService* 매개 변수입니다.  
  
3.  에 대 한 이벤트 처리기에는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> 이벤트 속성 클래스의 인스턴스를 추가 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectPropertiesRequestedEventArgs.PropertySources%2A> 이벤트 인수 매개 변수 컬렉션입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 두 개의 속성을 SharePoint 프로젝트에 추가 하는 방법을 보여 줍니다. 프로젝트 사용자 옵션 파일에 해당 데이터를 유지 하는 하나의 속성 (에서. csproj.user 파일 또는. vbproj.user 파일). 다른 속성이 프로젝트 파일 (.csproj 또는.vbproj)에 해당 데이터를 유지합니다.  
  
 [!code-vb[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#1)]
 [!code-csharp[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#1)]  
  
### <a name="understanding-the-code"></a>코드 이해  
 동일한 인스턴스에 충족 되도록는 `CustomProjectProperties` 클래스 될 때마다 사용 됩니다는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> 이벤트의 발생에 대 한 속성 개체를 추가 하는 코드 예제는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 이 이벤트가 발생 시점에 첫 번째 프로젝트의 속성입니다. 코드는이 이벤트가 다시 발생할 때마다이 개체를 검색 합니다. 사용 하는 방법에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 프로젝트에서 데이터 연결 속성 참조 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)합니다.  
  
 속성 값에 변경 내용을 유지는 **설정** 속성에 대 한 접근자 다음 Api를 사용 합니다.  
  
-   `CustomUserFileProperty`사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> 프로젝트 사용자 옵션 파일에 해당 값을 저장 하는 속성입니다.  
  
-   `CustomProjectFileProperty`사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> 메서드를 프로젝트 파일에 값을 저장 합니다.  
  
 이러한 파일에 데이터를 유지 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 시스템의 확장에 대 한 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)합니다.  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>사용자 지정 속성의 동작 지정  
 사용자 지정 속성 나타나고에서 동작을 정의할 수 있습니다는 **속성** 창에서 특성을 적용 하 여는 <xref:System.ComponentModel> 속성 정의에 네임 스페이스입니다. 다음 특성은 많은 시나리오에서 유용 합니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>:에 표시 되는 속성의 이름을 지정 합니다.는 **속성** 창.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>:의 맨 아래에 표시 되는 설명 문자열을 지정 합니다.는 **속성** 창에서 속성을 선택 합니다.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: 속성의 기본값을 지정합니다.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: 사용자 지정에 표시 되는 문자열 간의 변환을 지정는 **속성** 창과 문자열이 아닌 속성 값입니다.  
  
-   <xref:System.ComponentModel.EditorAttribute>: 속성을 수정 하는 데 사용자 지정 편집기를 지정 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.Shell  
  
-   Microsoft.VisualStudio.Shell.Interop  
  
-   Microsoft.VisualStudio.Shell.Interop.8.0  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 확장](../sharepoint/extending-sharepoint-projects.md)   
 [방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [방법: SharePoint 프로젝트에 바로 가기 메뉴 항목 추가](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  