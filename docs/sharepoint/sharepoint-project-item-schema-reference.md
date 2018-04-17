---
title: SharePoint 프로젝트 항목 스키마 참조 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperty element
- SafeControls element
- SafeControl element
- .spdata files
- ExtensionData element
- FeatureProperties element
- ProjectOutputFile element
- Files element
- ProjectItemFolder element
- ProjectItemFile element
- ExtensionDataItem element
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b039b1cf31a04a24819b03114c661a3ab1b108a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sharepoint-project-item-schema-reference"></a>SharePoint 프로젝트 항목 스키마 참조
  Visual Studio를 사용 하 여 SharePoint 프로젝트 항목 스키마.spdata 파일의 내용을 합니다. .Spdata 파일 내용과 SharePoint 프로젝트 항목의 동작을 지정합니다. SharePoint 프로젝트 항목의 내용에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
 SharePoint 프로젝트 항목 스키마 ProjectItemModelSchema.xsd 이름이 고 % Program Files (Visual Studio 11.0\Xml\Schemas x86)%\Microsoft 기본적으로 설치.  
  
 루트 요소는 [ProjectItem](../sharepoint/projectitem-element.md) 요소입니다. 다음 표에서 모든 스키마에 의해 정의 된 요소를 설명 합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint 프로젝트 항목에 연결 되어 있는 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.|  
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|SharePoint 프로젝트 항목 키/값 형식에 연관 된 사용자 지정 데이터 항목을 나타냅니다. 키와 값 모두 문자열 이어야 합니다.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint에 배포 될 때 기능과 함께 제공 되는 속성 값의 컬렉션을 나타냅니다. 기능이 배포 된 후에 코드에서 속성 값을 액세스할 수 있습니다.|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|SharePoint에 배포 될 때 기능과 함께 제공 되는 사용자 지정 속성을 나타냅니다. 기능이 배포 된 후에 코드에서 속성을 액세스할 수 있습니다.|  
|[파일](../sharepoint/files-element.md)|기능 요소 파일이 나 프로젝트의 출력 같은 SharePoint 프로젝트 항목을 함께 배포할 파일을 지정 합니다.|  
|[프로젝트 항목](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다.|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 기능 요소 파일 등의 SharePoint 파일을 나타냅니다.|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|매핑된 폴더를 나타냅니다.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|SharePoint에 배포 될 때 프로젝트 항목과 함께 포함할 프로젝트 출력을 나타냅니다.|  
|[SafeControl](../sharepoint/safecontrol-element.md)|ASPX 컨트롤 또는 SharePoint 사이트에서 모든 ASPX 페이지에 액세스 하려면 모든 사용자에 대 한 안전한 것으로 지정 하는 웹 파트를 나타냅니다.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|ASPX 컨트롤 및 모든 사용자는 SharePoint 사이트에서 ASPX 페이지에 액세스할 수에 대 한 안전한 것으로 지정 하는 웹 파트의 컬렉션을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목에 대한 항목 템플릿 및 프로젝트 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  