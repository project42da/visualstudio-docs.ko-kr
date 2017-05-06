---
title: "FeatureProperties Element"
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
  - "FeatureProperties element"
ms.assetid: 89233274-a842-4f40-a81a-5548379f6f39
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# FeatureProperties Element
  SharePoint에 배포될 때 기능과 함께 포함된 속성 값의 컬렉션을 나타냅니다.  기능이 배포된 후 코드에서 해당 속성 값에 액세스할 수 있습니다.  
  
## 구문  
  
```  
<FeatureProperties>  
  <FeatureProperty.../>  
</FeatureProperties>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|선택적 요소입니다.<br /><br /> 키\/값 형식으로 사용자 지정 속성을 나타냅니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.  .spdata 파일의 필수 루트 요소입니다.|  
  
## 설명  
 Feature 속성에 대한 자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)을 참조하십시오.  
  
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
  
  