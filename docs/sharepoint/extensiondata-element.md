---
title: "ExtensionData Element"
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
  - "ExtensionData element"
ms.assetid: caf6843b-dcf5-4688-a9eb-a424aae1beab
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# ExtensionData Element
  SharePoint 프로젝트 항목과 연결된 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.  
  
## 구문  
  
```  
<ExtensionData>  
  <ExtensionDataItem.../>  
</ExtensionData>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|선택적 요소입니다.<br /><br /> SharePoint 프로젝트 항목과 연결된 사용자 지정 데이터 항목을 키\/값 형식으로 나타냅니다.  키와 값은 모두 문자열이어야 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.  .spdata 파일의 필수 루트 요소입니다.|  
  
## 설명  
 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성을 사용하여 사용자 지정 데이터를 SharePoint 프로젝트 항목에 연결하면 Visual Studio는 프로젝트 항목에 대한 .spdata 파일에 있는 **ExtensionData** 요소에 데이터를 저장합니다.  자세한 내용은 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)을 참조하십시오.  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  