---
title: "How to: Add a Property to a Custom SharePoint Project Item Type | Microsoft Docs"
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
  - "SharePoint project items, defining your own types"
  - "project items [SharePoint development in Visual Studio], defining your own types"
  - "SharePoint development in Visual Studio, defining new project item types"
ms.assetid: 47e940f6-1779-4530-aea6-c43a370c544f
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# How to: Add a Property to a Custom SharePoint Project Item Type
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의하는 경우 프로젝트 항목에 속성을 추가할 수 있습니다.  **솔루션 탐색기**에서 프로젝트 항목을 선택하면 **속성** 창에 해당 속성이 표시됩니다.  
  
 다음 단계에서는 사용자 고유의 SharePoint 프로젝트 항목 형식이 이미 정의되어 있는 것으로 가정합니다.  자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)를 참조하십시오.  
  
### 프로젝트 항목 형식의 정의에 속성을 추가하려면  
  
1.  사용자 지정 프로젝트 항목 형식에 추가할 속성을 나타내는 공용 속성이 있는 클래스를 정의합니다.  사용자 지정 프로젝트 항목 형식에 여러 속성을 추가하려는 경우 모든 속성을 동일한 클래스 또는 서로 다른 여러 클래스에 정의할 수 있습니다.  
  
2.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드에서 *projectItemTypeDefinition* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 이벤트를 처리합니다.  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 이벤트의 이벤트 처리기에서 사용자 지정 속성 클래스의 인스턴스를 이벤트 인수 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> 컬렉션에 추가합니다.  
  
## 예제  
 다음 코드 예제에서는 **Example Property** 속성을 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/cs/extension/projectitemtypeproperty.cs#11)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.menuandproperty/vb/extension/projectitemtypeproperty.vb#11)]  
  
### 코드 이해  
 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> 이벤트가 발생할 때마다 `CustomProperties` 클래스의 동일한 인스턴스가 사용되도록 하기 위해 다음 코드 예제에서는 이 이벤트가 처음 발생하는 시점에 프로젝트 항목의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성에 속성 개체를 저장합니다.  이 코드에서는 이 이벤트가 다시 발생할 때마다 이 개체를 검색합니다.  <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 속성을 사용하여 프로젝트 항목에 데이터를 저장하는 방법에 대한 자세한 내용은 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)을 참조하십시오.  
  
 속성 값의 변경 내용을 유지하기 위해 `ExampleProperty`에 대한 **set** 접근자에서는 해당 속성과 연결된 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성에 새 값을 저장합니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성을 사용하여 프로젝트 항목에 데이터를 유지하는 방법에 대한 자세한 내용은 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)을 참조하십시오.  
  
### 사용자 지정 속성의 동작 지정  
 <xref:System.ComponentModel> 네임스페이스의 특성을 속성 정의에 적용하여 사용자 지정 속성이 **속성** 창에서 표시되고 동작하는 방식을 정의할 수 있습니다.  다음 특성은 여러 시나리오에서 유용합니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>. **속성** 창에 표시되는 속성의 이름을 지정합니다.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>. 속성을 선택할 때 **속성** 창의 아래쪽에 나타나는 설명 문자열을 지정합니다.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>. 속성의 기본값을 지정합니다.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>. **속성** 창에 나타나는 문자열과 문자열 이외의 속성 값 사이의 사용자 지정 변환을 지정합니다.  
  
-   <xref:System.ComponentModel.EditorAttribute>. 속성을 수정하는 데 사용할 사용자 지정 편집기를 지정합니다.  
  
## 코드 컴파일  
 이 코드 예제에는 다음 어셈블리에 대한 참조가 있는 클래스 라이브러리 프로젝트가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 하려면 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다.  자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
 프로젝트 항목을 배포하려면 어셈블리, 템플릿 및 프로젝트 항목과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [How to: Add a Shortcut Menu Item to a Custom SharePoint Project Item Type](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  