---
title: "SharePoint 프로젝트 시스템의 확장에 데이터를 저장 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SharePoint project items, saving string data
- project items [SharePoint development in Visual Studio], saving string data
- projects [SharePoint development in Visual Studio], saving string data
- SharePoint projects, saving string data
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 56cdfb95de6f0e5f8644ea3c73daacbf90e33a97
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="saving-data-in-extensions-of-the-sharepoint-project-system"></a>SharePoint 프로젝트 시스템의 확장에 데이터 저장
  SharePoint 프로젝트 시스템을 확장 하는 경우에 SharePoint 프로젝트를 닫은 후 유지 하는 문자열 데이터를 저장할 수 있습니다. 데이터는 특정 프로젝트 항목 또는와 프로젝트 자체에 일반적으로 관련 됩니다.  
  
 데이터를 유지할 필요가 없는 경우 구현 하는 SharePoint 도구 개체 모델의 개체에 데이터를 추가할 수 있습니다는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> 인터페이스입니다. 자세한 내용은 참조 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)합니다.  
  
## <a name="saving-data-that-is-associated-with-a-project-item"></a>와 연결 된 데이터를 저장 하는 프로젝트 항목  
 프로젝트 항목에 추가 하는 속성의 값과 같은 특정 SharePoint 프로젝트 항목을 연관 된 데이터가 있는 경우에 프로젝트 항목에 대 한.spdata 파일에는 데이터를 저장할 수 있습니다. 이 위해 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 개체입니다. 이 속성에 추가 하는 데이터가 저장 되는 **ExtensionData** 프로젝트 항목에 대 한.spdata 파일의 요소입니다. 자세한 내용은 참조 [ExtensionData 요소](../sharepoint/extensiondata-element.md)합니다.  
  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성 사용자 지정 SharePoint 프로젝트 항목 형식에 정의 된 문자열 속성의 값을 저장 합니다. 이 예를 보려면이 컨텍스트에서 보다 큰 예제의 참조 하세요. [하는 방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)합니다.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#14)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#14)]  
  
## <a name="saving-data-that-is-associated-with-a-project"></a>와 연결 된 데이터를 저장 하는 프로젝트  
 SharePoint 프로젝트에 추가 하는 속성의 값과 같은 프로젝트 수준 데이터가 있는 경우 프로젝트 파일 (.csproj 파일 또는.vbproj 파일) 또는 프로젝트 사용자 옵션 파일에 데이터를 저장할 수 있습니다 (에서. csproj.user 파일 또는. vbproj.user 파일). 데이터를 저장 하도록 선택한 파일 데이터를 사용할 수는 방법에 따라 달라 집니다.  
  
-   모든 개발자가 SharePoint 프로젝트에 사용할 수 있도록 데이터를 원하는 경우 프로젝트 파일에 데이터를 저장 합니다. 이 파일은 항상 체크 인 소스 제어 데이터베이스에이 파일에 데이터를 다른 개발자는 프로젝트를 체크 아웃가 사용할 수 있도록 합니다.  
  
-   SharePoint 프로젝트가 Visual Studio에서 열려 있는 현재 개발자만 사용할 수 있도록 데이터를 원하는 경우 프로젝트 사용자 옵션 파일에 데이터를 저장 합니다. 이 파일은 일반적으로 체크 인 되지 소스 제어 데이터베이스에 이므로이 파일의에서 데이터를 다른 개발자는 프로젝트를 체크 아웃가 사용할 수 없습니다.  
  
### <a name="saving-data-to-the-project-file"></a>프로젝트 파일에 데이터 저장  
 프로젝트 파일에 데이터를 저장 하려면 변환는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> 개체를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> 메서드. 다음 코드 예제에서는 프로젝트 파일을 프로젝트 속성의 값을 저장 하려면이 메서드를 사용 하는 방법을 보여 줍니다. 큰 샘플의 컨텍스트에서이 예제를 보려면 [하는 방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)합니다.  
  
 [!code-vb[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#3)]
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#3)]  
  
 변환에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> Visual Studio 자동화 개체 모델 또는 통합 개체 모델에서 다른 형식으로 개체 참조 [변환 간의 SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식 ](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
### <a name="saving-data-to-the-project-user-option-file"></a>프로젝트 사용자 옵션 파일에 데이터를 저장합니다.  
 프로젝트 사용자 옵션 파일에 데이터를 저장 하려면 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> 속성은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체입니다. 다음 코드 예제에서는 프로젝트 사용자 옵션 파일을 프로젝트 속성의 값을 저장 하려면이 속성을 사용 하는 방법을 보여 줍니다. 큰 샘플의 컨텍스트에서이 예제를 보려면 [하는 방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)합니다.  
  
 [!code-vb[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#2)]
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#2)]  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)   
 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식 간의 변환](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)  
  
  