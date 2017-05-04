---
title: "ProjectItemFolder Element | Microsoft Docs"
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
  - "ProjectItemFolder element"
ms.assetid: 15b386dd-f523-4425-9fcc-517325681358
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# ProjectItemFolder Element
  매핑된 폴더를 나타냅니다.  
  
## 구문  
  
```  
<ProjectItemFolder Target = "Path of SharePoint folder the mapped folder corresponds to"  
    Type = "Type of deployment for the mapped folder" />  
```  
  
## 형식  
 **ProjectItemFolderType**  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**Target**|필수 **xs:string** 특성입니다.<br /><br /> 배포 루트 폴더에 상대적인 매핑된 폴더가 대응하는 SharePoint 설치의 폴더 경로입니다.  배포 루트 폴더는 **Type** 특성으로 지정된 배포 형식에 의해 결정됩니다.<br /><br /> 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Path** 및 **Deployment Root** 속성에 대한 설명을 참조하십시오.|  
|**Type**|필수 **xs:string** 특성입니다.<br /><br /> 매핑된 폴더에 대한 배포 형식입니다.  가능한 값에 대한 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Type** 속성에 대한 설명을 참조하십시오.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.  .spdata 파일의 필수 루트 요소입니다.|  
  
## 설명  
 매핑된 폴더에 대한 자세한 내용은 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)을 참조하십시오.  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  