---
title: ProjectItem 요소 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ea55cbba9115b88ab9bbf763ec489dce7ad7556e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="projectitem-element"></a>ProjectItem 요소
  SharePoint 프로젝트 항목을 나타냅니다. .Spdata 파일의 필수 루트 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```  
<ProjectItem DefaultFile = "File that opens in the editor when you open the project item"  
    FeatureReceiverClass = "Class that implements a feature receiver for the project item"  
    FeatureReceiverAssembly = "Assembly that defines a feature receiver for the project item"  
    SupportedTrustLevels = "Trust levels that the project item supports"  
    SupportedDeploymentScopes = "Deployment scopes that the project item supports"  
    Type="Identifier for the project item">  
  <Files>...</Files>  
  <ProjectItemFolder>...</ProjectItemFolder>  
  <SafeControls>...</SafeControls>  
  <FeatureProperties>...</FeatureProperties>  
  <ExtensionData>...</ExtensionData>  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**DefaultFile**|선택적 **xs: string** 특성입니다.<br /><br /> SharePoint 프로젝트 항목을 열 때 Visual Studio 편집기에서 열려 있는 파일의 파일 이름을 포함 하 여 상대 경로 **솔루션 탐색기**합니다. .Spdata 파일을 포함 하는 폴더에서 상대 경로가입니다.|  
|**FeatureReceiverClass**|선택적 **xs: string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목에 대 한 기능 수신기 클래스의 정규화 된 이름입니다. 기능 수신기에 대 한 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다.|  
|**FeatureReceiverAssembly**|선택적 **xs: string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목에 대 한 기능 수신기를 정의 하는 어셈블리의 정규화 된 이름을 지정 합니다. 기능 수신기에 대 한 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다. 정규화 된 어셈블리 이름에 대 한 자세한 내용은 참조 [어셈블리 이름을](/dotnet/framework/app-domains/assembly-names)합니다.|  
|**SupportedTrustLevels**|선택적 **xs: string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목을 지원 하는 신뢰 수준을 지정 합니다. 이 값은 다음 문자열 중 하나일 수 있습니다: 샌드박스, FullTrust 또는 모든 합니다. 값 Sandboxed 및 FullTrust 파트를 모두 지정 합니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 항목 형식에서이 특성의 값을 할당 하는 값에 해당는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> 속성의 구현에는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드. 이 특성에 대해 다른 값을 지정 하면 Visual Studio를 덮어씁니다 값에서 지정 하는 동일한 신뢰 수준을 지정 하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> 속성입니다.|  
|**SupportedDeploymentScopes**|선택적 **xs: string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목을 지원 하 여 배포 범위를 지정 합니다. 이 값은 다음 문자열 중 하나 이상의 구성 된 쉼표로 구분 된 문자열: 팜, 사이트, 웹, 웹 응용 프로그램 또는 패키지입니다. 예를 들어 "Web에서 사이트"입니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 항목 형식에서이 특성의 값을 할당 하는 값에 해당는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> 속성의 구현에는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드. 이 특성에 대해 다른 값을 지정 하면 Visual Studio를 덮어씁니다 값에서 지정 하는 동일한 신뢰 수준을 지정 하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> 속성입니다.|  
|**Type**|필요한 **xs: string** 특성입니다.<br /><br /> SharePoint 프로젝트 항목에 대 한 식별자입니다. 식별자의 문자열에 전달 하는 사용자 지정 SharePoint 프로젝트 항목 형식에는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)합니다.<br /><br /> Visual Studio에 포함 된 기본 제공 SharePoint 프로젝트 항목에 대 한 식별자 목록, 참조 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|선택적 요소입니다.<br /><br /> SharePoint 프로젝트 항목에 연결 되어 있는 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.<br /><br /> 하나만 포함 될 수 **ExtensionData** 요소입니다.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|선택적 요소입니다.<br /><br /> SharePoint에 배포 될 때 기능과 함께 제공 되는 속성 값의 컬렉션을 나타냅니다.<br /><br /> 하나만 포함 될 수 **FeatureProperties** 요소입니다.|  
|[파일](../sharepoint/files-element.md)|선택적 **FileCollectionType** 요소입니다.<br /><br /> 종속 비 SharePoint 프로젝트의 출력 이어서 기능 요소 파일 같은 SharePoint 프로젝트 항목을 함께 배포할 파일을 지정 합니다.<br /><br /> 하나를 포함 해야는 **파일** 또는 **ProjectItemFolder** 요소 중 하나만 있습니다.|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|선택적 **ProjectItemFolderType** 요소입니다.<br /><br /> 매핑된 폴더를 나타냅니다.<br /><br /> 하나를 포함 해야는 **파일** 또는 **ProjectItemFolder** 요소 중 하나만 있습니다.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|선택적 요소입니다.<br /><br /> ASPX 컨트롤 및 모든 사용자는 SharePoint 사이트에서 ASPX 페이지에 액세스할 수에 대 한 안전한 것으로 지정 하는 웹 파트의 컬렉션을 나타냅니다.<br /><br /> 하나만 포함 될 수 **SafeControls** 요소입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
 없음  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  