---
title: "ProjectOutputFile 요소 | Microsoft Docs"
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
helpviewer_keywords: ProjectOutputFile element
ms.assetid: 52a017bf-e19c-49e4-bb8f-cbe6958195c2
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a397648dd81ead8134777c8b36982fa6b65b687b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile 요소
  SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 별도 프로젝트의 출력을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>형식  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**ProjectId**|필요한 **xs: string** 특성입니다.<br /><br /> 에 포함 하려는 출력이 종속 프로젝트의 GUID입니다. 이에 해당 하는 **ProjectGuid** 종속 프로젝트 파일의 요소입니다.|  
|**프로젝트 경로**|필요한 **xs: string** 특성입니다.<br /><br /> 에 포함 하려는 출력이 종속 프로젝트의 프로젝트 파일 이름을 포함 하 여 상대 경로입니다. 이 경로 SharePoint 프로젝트 항목을 포함 하는 SharePoint 프로젝트의 루트 폴더에 상대적입니다.|  
|**Target**|선택적 **xs: string** 특성입니다.<br /><br /> 종속 프로젝트 출력을 배포 루트 폴더에 상대적인 SharePoint 서버에 배포 하는 위치 경로입니다. 배포 루트 폴더에서 지정 된 배포 유형에 따라 결정 됩니다는 **형식** 특성입니다.<br /><br /> 자세한 내용은 설명을 참조는 **배포 경로** 및 **배포 루트** 속성을 SharePoint 프로젝트 항목에 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|필요한 **xs: string** 특성입니다.<br /><br /> 종속 프로젝트의 출력에 사용할 배포의 형식입니다. 가능한 값에 대 한 자세한 정보에 대 한 설명을 참조는 **배포 유형을** 에서 SharePoint 프로젝트 항목의 속성 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[파일](../sharepoint/files-element.md)|SharePoint에 배포 될 때 SharePoint 프로젝트 항목에 포함할 파일을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여는 **ProjectOutputFile** SharePoint 프로젝트 항목의 배포에는 프로젝트의 출력을 포함 하는 요소입니다. 다른 프로젝트 또는 프로젝트 항목을 포함 하는 동일한 프로젝트를 지정할 수 있습니다. 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [패키지 및 프로젝트 항목에 대 한 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  