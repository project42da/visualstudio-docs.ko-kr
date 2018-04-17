---
title: 파일 요소 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d75041c1b0202eecd5769773efbcfce9c53ec4ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="files-element"></a>Files 요소
  종속 비 SharePoint 프로젝트의 출력 이어서 기능 요소 파일 같은 SharePoint 프로젝트 항목을 함께 배포할 파일을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>형식  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|선택적 **ProjectItemFileType** 요소입니다.<br /><br /> SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 기능 요소 파일 등의 SharePoint 파일을 나타냅니다.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|선택적 **ProjectOutputFileType** 요소입니다.<br /><br /> SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 프로젝트 출력을 나타냅니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[프로젝트 항목](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다. .Spdata 파일의 필수 루트 요소입니다.|  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  