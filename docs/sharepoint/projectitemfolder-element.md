---
title: "ProjectItemFolder 요소 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: ProjectItemFolder element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: df3c5b91e5f95d6ec794bff08c2251c5bf5e5307
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="projectitemfolder-element"></a>ProjectItemFolder 요소
  매핑된 폴더를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectItemFolder Target = "Path of SharePoint folder the mapped folder corresponds to"  
    Type = "Type of deployment for the mapped folder" />  
```  
  
## <a name="type"></a>형식  
 **ProjectItemFolderType**  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**Target**|필요한 **xs: string** 특성입니다.<br /><br /> 배포 루트 폴더에 상대적인,에 해당 하는 매핑된 폴더는 SharePoint 설치의 폴더의 경로입니다. 배포 루트 폴더에서 지정 된 배포 유형에 따라 결정 됩니다는 **형식** 특성입니다.<br /><br /> 자세한 내용은 설명을 참조는 **배포 경로** 및 **배포 루트** 속성을 SharePoint 프로젝트 항목에 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|필요한 **xs: string** 특성입니다.<br /><br /> 매핑된 폴더에 대 한 배포의 형식입니다. 가능한 값에 대 한 자세한 정보에 대 한 설명을 참조는 **배포 유형을** 에서 SharePoint 프로젝트 항목의 속성 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[프로젝트 항목](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다. .Spdata 파일의 필수 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 매핑된 폴더에 대 한 자세한 내용은 참조 [하는 방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  