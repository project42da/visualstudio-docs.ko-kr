---
title: "SafeControl Element"
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
  - "SafeControl element"
ms.assetid: e7c61749-fc73-412c-be30-4af5ff2a9fd2
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# SafeControl Element
  사용자가 SharePoint 사이트의 모든 ASPX 페이지에서 액세스하는 데 안전한 것으로 지정된 ASPX 컨트롤 또는 웹 파트를 나타냅니다.  
  
## 구문  
  
```  
<SafeControl Assembly = "Name of assembly that contains the safe control"  
    IsSafe = "true/false"  
    IsSafeAgainstScript = "true/false"  
    Name = "Name of this safe control entry"  
    Namespace = "Namespace of the safe control"  
    TypeName = "Type of the safe control" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**Assembly**|선택적 **xs:string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트가 정의된 어셈블리의 이름입니다.  기본적으로 이 특성은 어셈블리 이름에 대한 **$SharePoint.Project.AssemblyFullName$** 대체 가능한 매개 변수를 사용합니다.  자세한 내용은 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)를 참조하십시오.|  
|**IsSafe**|선택적 **xs:boolean** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트가 신뢰할 수 없는 사용자가 액세스할 수 있을 만큼 안전한지 여부를 지정합니다.|  
|**IsSafeAgainstScript**|선택적 **xs:boolean** 특성입니다.<br /><br /> 신뢰할 수 없는 사용자가 ASPX 컨트롤 또는 웹 파트의 속성을 보거나 편집할 수 있는지 여부를 지정합니다.|  
|**Name**|선택적 **xs:string** 특성입니다.<br /><br /> 컬렉션에서 이 안전 제어 항목의 이름입니다.|  
|**Namespace**|선택적 **xs:string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트의 네임스페이스입니다.|  
|**TypeName**|선택적 **xs:string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트의 형식 이름입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[SafeControls](../sharepoint/safecontrols-element.md)|사용자가 SharePoint 사이트의 모든 ASPX 페이지에서 액세스하는 데 안전한 것으로 지정된 ASPX 컨트롤 또는 웹 파트의 컬렉션을 나타냅니다.|  
  
## 설명  
 안전 컨트롤에 대한 자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)를 참조하십시오.  
  
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
  
  