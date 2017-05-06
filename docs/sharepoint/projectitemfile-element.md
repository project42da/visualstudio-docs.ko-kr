---
title: "ProjectItemFile Element"
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
  - "ProjectItemFile element"
ms.assetid: 68d44d31-625a-4f02-b998-463ac0ffb2ef
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# ProjectItemFile Element
  SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 Feature 요소 파일과 같은 SharePoint 파일을 나타냅니다.  
  
## 구문  
  
```  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## 형식  
 **ProjectItemFileType**  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**Source**|필수 **xs:string** 특성입니다.<br /><br /> 프로젝트 항목과 함께 배포할 파일의 이름입니다.|  
|**Target**|선택적 **xs:string** 특성입니다.<br /><br /> 파일을 SharePoint에 배포할 경로로, 배포 루트 폴더에 상대적인 경로입니다.  배포 루트 폴더는 **Type** 특성으로 지정된 배포 형식에 의해 결정됩니다.  **Target** 특성을 지정하지 않을 경우 파일은 **Source** 특성에 지정된 이름을 가진 폴더에 배포됩니다.<br /><br /> 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Path** 및 **Deployment Root** 속성에 대한 설명을 참조하십시오.|  
|**Type**|필수 **xs:string** 특성입니다.<br /><br /> 파일에 대한 배포 형식입니다.  가능한 값에 대한 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Type** 속성에 대한 설명을 참조하십시오.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Files](../sharepoint/files-element.md)|SharePoint에 배포할 때 SharePoint 프로젝트 항목과 함께 포함할 파일을 지정합니다.|  
  
## 설명  
 일반적으로 **ProjectItemFile** 요소에서 참조되는 SharePoint파일에는 Feature 요소 파일\(Elements.xml\), 목록 정의용 스키마 파일\(Schema.xml\) 및 웹 부품용 웹 파트 정의 파일\(.webpart\)이 있습니다.  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  