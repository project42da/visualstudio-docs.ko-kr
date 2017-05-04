---
title: "ProjectOutputFile Element | Microsoft Docs"
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
  - "ProjectOutputFile element"
ms.assetid: 52a017bf-e19c-49e4-bb8f-cbe6958195c2
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# ProjectOutputFile Element
  SharePoint에 배포될 때 프로젝트 항목과 함께 포함할 별도의 프로젝트의 출력을 나타냅니다.  
  
## 구문  
  
```  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## 형식  
 **ProjectOutputFileType**  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**ProjectId**|필수 **xs:string** 특성입니다.<br /><br /> 포함할 출력이 있는 종속 프로젝트의 GUID입니다.  종속 프로젝트 파일에서 **ProjectGuid** 요소에 해당합니다.|  
|**ProjectPath**|필수 **xs:string** 특성입니다.<br /><br /> 포함할 출력이 있는 종속 프로젝트의 경로 이름\(프로젝트 파일 이름 포함\)입니다.  이 경로는 SharePoint 프로젝트 항목을 포함하는 SharePoint 프로젝트의 루트 폴더에 상대적입니다.|  
|**Target**|선택적 **xs:string** 특성입니다.<br /><br /> 배포 루트 폴더에 상대적인 SharePoint 서버에 종속 프로젝트 출력을 배포할 경로입니다.  배포 루트 폴더는 **Type** 특성으로 지정된 배포 형식에 의해 결정됩니다.<br /><br /> 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Path** 및 **Deployment Root** 속성에 대한 설명을 참조하십시오.|  
|**Type**|필수 **xs:string** 특성입니다.<br /><br /> 종속 프로젝트의 출력에 사용할 배포 형식입니다.  가능한 값에 대한 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)에 있는 SharePoint 프로젝트 항목의 **Deployment Type** 속성에 대한 설명을 참조하십시오.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Files](../sharepoint/files-element.md)|SharePoint에 배포할 때 SharePoint 프로젝트 항목과 함께 포함할 파일을 지정합니다.|  
  
## 설명  
 **ProjectOutputFile** 요소를 사용하여 SharePoint 프로젝트 항목의 배포에서 프로젝트의 출력을 포함합니다.  다른 프로젝트 또는 프로젝트 항목을 포함하는 동일한 프로젝트를 지정할 수 있습니다.  자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)를 참조하십시오.  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  