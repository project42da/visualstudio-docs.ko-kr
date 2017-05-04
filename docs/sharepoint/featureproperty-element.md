---
title: "FeatureProperty Element | Microsoft Docs"
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
ms.assetid: 36a771a6-98d0-4a40-a278-d76baea82452
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# FeatureProperty Element
  SharePoint에 배포될 때 기능과 함께 포함된 사용자 지정 속성을 나타냅니다.  기능이 배포된 후 코드에서 해당 속성에 액세스할 수 있습니다.  
  
## 구문  
  
```  
<FeatureProperty Key = "Key of the property value"  
    Value = "Property value" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**Key**|필수 **xs:string** 특성입니다.<br /><br /> 속성 값을 저장하고 검색하는 데 사용되는 키입니다.  각 속성은 기능 내에서 고유한 키가 있어야 합니다.|  
|**Value**|필수 **xs:string** 특성입니다.<br /><br /> 속성 값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint에 배포될 때 기능과 함께 포함된 속성 값의 컬렉션을 나타냅니다.|  
  
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
  
  