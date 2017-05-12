---
title: "SharePoint Project Item Schema Reference"
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
  - "FeatureProperty element"
  - "SafeControls element"
  - "SafeControl element"
  - ".spdata files"
  - "ExtensionData element"
  - "FeatureProperties element"
  - "ProjectOutputFile element"
  - "Files element"
  - "ProjectItemFolder element"
  - "ProjectItemFile element"
  - "ExtensionDataItem element"
  - "ProjectItem element"
ms.assetid: 12b63cbc-bf94-4175-bfa8-2117943d00d1
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# SharePoint Project Item Schema Reference
  Visual Studio에서는 SharePoint 프로젝트 항목 스키마를 사용하여 .spdata 파일 내용의 유효성을 검사합니다.  .spdata 파일은 SharePoint 프로젝트 항목의 내용과 동작을 지정합니다.  SharePoint 프로젝트 항목의 내용에 대한 자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
 SharePoint 프로젝트 항목 스키마는 ProjectItemModelSchema.xsd로 이름이 지정되며 %Program Files \(x86\)%\\Microsoft Visual Studio 11.0\\Xml\\Schemas에 기본적으로 설치됩니다.  
  
 루트 요소는 [ProjectItem](../sharepoint/projectitem-element.md) 요소입니다.  다음 표에서는 스키마에서 정의된 모든 요소에 대해 설명합니다.  
  
|요소|설명|  
|--------|--------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint 프로젝트 항목과 연결된 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.|  
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|SharePoint 프로젝트 항목과 연결된 사용자 지정 데이터 항목을 키\/값 형식으로 나타냅니다.  키와 값은 모두 문자열이어야 합니다.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint에 배포될 때 기능과 함께 포함된 속성 값의 컬렉션을 나타냅니다.  기능이 배포된 후 코드에서 해당 속성 값에 액세스할 수 있습니다.|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|SharePoint에 배포될 때 기능과 함께 포함된 사용자 지정 속성을 나타냅니다.  기능이 배포된 후 코드에서 해당 속성에 액세스할 수 있습니다.|  
|[Files](../sharepoint/files-element.md)|Feature 요소 파일, 프로젝트 출력 등, SharePoint 프로젝트 항목과 함께 배포할 파일을 지정합니다.|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 Feature 요소 파일과 같은 SharePoint 파일을 나타냅니다.|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|매핑된 폴더를 나타냅니다.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 프로젝트의 출력을 나타냅니다.|  
|[SafeControl](../sharepoint/safecontrol-element.md)|사용자가 SharePoint 사이트의 모든 ASPX 페이지에서 액세스하는 데 안전한 것으로 지정된 ASPX 컨트롤 또는 웹 파트를 나타냅니다.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|사용자가 SharePoint 사이트의 모든 ASPX 페이지에서 액세스하는 데 안전한 것으로 지정된 ASPX 컨트롤 또는 웹 파트의 컬렉션을 나타냅니다.|  
  
## 참고 항목  
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  