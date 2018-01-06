---
title: "FeatureProperty 요소 | Microsoft Docs"
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
helpviewer_keywords: FeatureProperty element
ms.assetid: 36a771a6-98d0-4a40-a278-d76baea82452
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0f1576c23b409226501637ada8d12d2320dd3c37
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="featureproperty-element"></a>FeatureProperty 요소
  SharePoint에 배포 될 때 기능과 함께 제공 되는 사용자 지정 속성을 나타냅니다. 기능이 배포 된 후에 코드에서 속성을 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<FeatureProperty Key = "Key of the property value"  
    Value = "Property value" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**키**|필요한 **xs: string** 특성입니다.<br /><br /> 저장 하 고 속성 값을 검색 하는 데 사용 되는 키입니다. 각 속성의 기능 내에서 고유한 키를 있어야 합니다.|  
|**값**|필요한 **xs: string** 특성입니다.<br /><br /> 속성 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint에 배포 될 때 기능과 함께 제공 되는 속성 값의 컬렉션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 기능 속성에 대 한 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  