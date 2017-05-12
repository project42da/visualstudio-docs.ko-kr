---
title: "Files Element"
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
  - "Files element"
ms.assetid: 3c611d5b-28f1-48a7-a068-63e01fa2f3aa
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# Files Element
  Feature 요소 파일 및 종속된 비 SharePoint 프로젝트 출력 등, SharePoint 프로젝트 항목과 함께 배포할 파일을 지정합니다.  
  
## 구문  
  
```  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## 형식  
 **FileCollectionType**  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|선택적 **ProjectItemFileType** 요소입니다.<br /><br /> SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 Feature 요소 파일과 같은 SharePoint 파일을 나타냅니다.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|선택적 **ProjectOutputFileType** 요소입니다.<br /><br /> SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 프로젝트의 출력을 나타냅니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.  .spdata 파일의 필수 루트 요소입니다.|  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  