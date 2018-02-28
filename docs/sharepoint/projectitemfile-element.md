---
title: "ProjectItemFile 요소 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 7c222c25417f9a33f28871c94d8dd0d9353e1e76
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="projectitemfile-element"></a>ProjectItemFile 요소
  SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 기능 요소 파일 등의 SharePoint 파일을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## <a name="type"></a>형식  
 **ProjectItemFileType**  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**소스**|필요한 **xs: string** 특성입니다.<br /><br /> 프로젝트 항목과 함께 배포 하는 파일의 이름입니다.|  
|**Target**|선택적 **xs: string** 특성입니다.<br /><br /> 배포 루트 폴더에 상대적인 SharePoint에서 파일이 배포 되는 경로입니다. 배포 루트 폴더에서 지정 된 배포 유형에 따라 결정 됩니다는 **형식** 특성입니다. 경우는 **대상** 특성이 지정 되지 않은에 지정 된 이름의 파일이 폴더에 배포 된 **소스** 특성입니다.<br /><br /> 자세한 내용은 설명을 참조는 **배포 경로** 및 **배포 루트** 속성을 SharePoint 프로젝트 항목에 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|필요한 **xs: string** 특성입니다.<br /><br /> 형식 파일에 대 한 배포입니다. 가능한 값에 대 한 자세한 정보에 대 한 설명을 참조는 **배포 유형을** 에서 SharePoint 프로젝트 항목의 속성 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[파일](../sharepoint/files-element.md)|SharePoint에 배포 될 때 SharePoint 프로젝트 항목에 포함할 파일을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 참조 되는 SharePoint 파일 **ProjectItemFile** 기능 요소 (Elements.xml) 파일, 목록 정의 (Schema.xml)에 대 한 스키마 파일 및 웹 파트 정의 파일 (.webpart) 웹 파트에 대 한 요소를 포함 합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  