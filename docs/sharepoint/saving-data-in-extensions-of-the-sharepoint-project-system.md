---
title: "Saving Data in Extensions of the SharePoint Project System | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SharePoint project items, saving string data"
  - "project items [SharePoint development in Visual Studio], saving string data"
  - "projects [SharePoint development in Visual Studio], saving string data"
  - "SharePoint projects, saving string data"
ms.assetid: 903b9da7-2eea-404c-9a7a-7bc15cb90d6c
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# Saving Data in Extensions of the SharePoint Project System
  SharePoint 프로젝트 시스템을 확장하는 경우 SharePoint 프로젝트가 닫힌 후에도 유지되는 문자열 데이터를 저장할 수 있습니다.  이 데이터는 일반적으로 특정 프로젝트 항목 또는 프로젝트 자체와 연결됩니다.  
  
 유지할 필요가 없는 데이터가 있는 경우 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> 인터페이스를 구현하는 SharePoint 도구 개체 모델의 어떠한 개체에도 데이터를 추가할 수 있습니다.  자세한 내용은 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)을 참조하십시오.  
  
## 프로젝트 항목과 연결된 데이터 저장  
 프로젝트 항목에 추가하는 속성의 값과 같이 특정 SharePoint 프로젝트 항목과 연결된 데이터가 있는 경우 프로젝트 항목에 대한 .spdata 파일에 데이터를 저장할 수 있습니다.  이렇게 하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성을 사용합니다.  이 속성에 추가한 데이터는 프로젝트 항목에 대한 .spdata 파일의 **ExtensionData** 요소에 저장됩니다.  자세한 내용은 [ExtensionData Element](../sharepoint/extensiondata-element.md)를 참조하십시오.  
  
 다음 코드 예제에서는 사용자 지정 SharePoint 프로젝트 항목 형식에 정의된 문자열 속성의 값을 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성을 사용하여 저장하는 방법을 보여 줍니다.  보다 큰 예제의 컨텍스트에서 이 예제를 보려면 [How to: Add a Property to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)를 참조하십시오.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/cs/extension/projectitemtypeproperty.cs#14)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/vb/extension/projectitemtypeproperty.vb#14)]  
  
## 프로젝트와 연결된 데이터 저장  
 SharePoint 프로젝트에 추가하는 속성의 값과 같은 프로젝트 수준 데이터가 있는 경우 프로젝트 파일\(.csproj 파일 또는 .vbproj 파일\) 또는 프로젝트 사용자 옵션 파일\(.csproj.user 파일 또는 .vbproj.user 파일\)에 데이터를 저장할 수 있습니다.  데이터를 저장하기 위해 선택하는 파일은 데이터를 사용할 방법에 따라 달라집니다.  
  
-   SharePoint 프로젝트를 여는 모든 개발자가 데이터를 사용할 수 있게 하려면 프로젝트 파일에 데이터를 저장합니다.  이 파일은 항상 소스 제어 데이터베이스에 체크 인되므로 이 파일의 데이터는 프로젝트를 체크 아웃하는 다른 개발자가 사용할 수 있습니다.  
  
-   Visual Studio에서 SharePoint 프로젝트를 열어 놓은 현재 개발자만 데이터를 사용할 수 있게 하려면 프로젝트 사용자 옵션 파일에 데이터를 저장합니다.  이 파일은 일반적으로 소스 제어 데이터베이스에 체크 인되지 않으므로 이 파일의 데이터는 프로젝트를 체크 아웃하는 다른 개발자가 사용할 수 없습니다.  
  
### 프로젝트 파일에 데이터 저장  
 프로젝트 파일에 데이터를 저장하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> 개체로 변환한 다음 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> 메서드를 사용합니다.  다음 코드 예제에서는 이 메서드를 사용하여 프로젝트 속성의 값을 프로젝트 파일에 저장하는 방법을 보여 줍니다.  보다 큰 예제의 컨텍스트에서 이 예제를 보려면 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)를 참조하십시오.  
  
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../snippets/csharp/VS_Snippets_OfficeSP/spext_spcustomprjproperty/cs/customspproperty/customproperty.cs#3)]
 [!code-vb[SpExt_SPCustomPrjProperty#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spext_spcustomprjproperty/vb/customspproperty/customproperty.vb#3)]  
  
 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체를 Visual Studio 자동화 개체 모델 또는 통합 개체 모델의 다른 형식으로 변환하는 방법에 대한 자세한 내용은 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)을 참조하십시오.  
  
### 프로젝트 사용자 옵션 파일에 데이터 저장  
 프로젝트 사용자 옵션 파일에 데이터를 저장하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> 속성을 사용합니다.  다음 코드 예제에서는 이 속성을 사용하여 프로젝트 속성의 값을 프로젝트 사용자 옵션 파일에 저장하는 방법을 보여 줍니다.  보다 큰 예제의 컨텍스트에서 이 예제를 보려면 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)를 참조하십시오.  
  
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../snippets/csharp/VS_Snippets_OfficeSP/spext_spcustomprjproperty/cs/customspproperty/customproperty.cs#2)]
 [!code-vb[SpExt_SPCustomPrjProperty#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spext_spcustomprjproperty/vb/customspproperty/customproperty.vb#2)]  
  
## 참고 항목  
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)  
  
  