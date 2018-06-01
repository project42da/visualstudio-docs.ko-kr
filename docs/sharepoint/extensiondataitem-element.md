---
title: ExtensionDataItem 요소 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionDataItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 48c29cb41c80d75c6f873171b7e9c758a2513612
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691939"
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem 요소
  연결 된 SharePoint 프로젝트 항목 키/값 형식에는 사용자 지정 데이터 항목입니다. 키와 값 모두 문자열 이어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<ExtensionDataItem Key = "Key of the data item"  
    Value = "Value of the data item" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**키**|필요한 **xs: string** 특성입니다.<br /><br /> 데이터 저장과 데이터 항목을 검색 하는 데 사용 되는 키입니다.|  
|**값**|필요한 **xs: string** 특성입니다.<br /><br /> 데이터 항목의 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint 프로젝트 항목에 연결 되어 있는 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 SharePoint 프로젝트 항목으로 사용자 지정 데이터를 연결 하는 경우는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> 속성의는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> 개체를 새 데이터를 저장 하는 Visual Studio **ExtensionDataItem** 요소에는 `.spdata` 파일에서 프로젝트 항목입니다. 자세한 내용은 참조 [SharePoint 프로젝트 시스템의 확장에 대 한 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel| 
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  