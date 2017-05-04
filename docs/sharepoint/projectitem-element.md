---
title: "ProjectItem Element | Microsoft Docs"
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
  - "ProjectItem element"
ms.assetid: df588235-12a1-4798-bc56-ef81843de17f
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# ProjectItem Element
  SharePoint 프로젝트 항목을 나타냅니다.  .spdata 파일의 필수 루트 요소입니다.  
  
## 구문  
  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**DefaultFile**|선택적 **xs:string** 특성입니다.<br /><br /> **솔루션 탐색기**에서 SharePoint 프로젝트 항목을 열 때 Visual Studio 편집기에서 열리는 파일의 상대 경로\(파일 이름 포함\)입니다.  경로는 .spdata 파일이 포함된 폴더의 상대 경로입니다.|  
|**FeatureReceiverClass**|선택적 **xs:string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목에 대한 기능 수신기 클래스의 정규화된 이름입니다.  기능 수신기에 대한 자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)를 참조하십시오.|  
|**FeatureReceiverAssembly**|선택적 **xs:string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 팀에 대한 기능 수신기를 정의하는 어셈블리의 정규화된 이름을 지정합니다.  기능 수신기에 대한 자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)를 참조하십시오.  정규화된 어셈블리 이름에 대한 자세한 내용은 [어셈블리 이름](http://msdn.microsoft.com/library/8f8c2c90-f15d-400e-87e7-a757e4f04d0e)을 참조하십시오.|  
|**SupportedTrustLevels**|선택적 **xs:string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목이 지원하는 신뢰 수준을 지정합니다.  이 값은 Sandboxed, FullTrust 또는 All 문자열 중 하나가 될 수 있습니다.  값 모두는 Sandboxed 및 FullTrust를 모두 지정합니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 항목 형식에서 이 특성의 값을 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> 메서드의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 속성에 할당할 값에 해당합니다.  이 특성에 다른 값을 지정할 경우 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> 속성에서 지정한 동일한 신뢰 수준을 지정하는 있도록 Visual Studio 값을 덮어씁니다.|  
|**SupportedDeploymentScopes**|선택적 **xs:string** 특성입니다.<br /><br /> 이 SharePoint 프로젝트 항목이 지원하는 배포 범위를 지정합니다.  이 값은 팜, 사이트, 웹, WebApplication 또는 패키지 같은 하나 이상의 문자열로 구성된 쉼표로 구분된 문자열입니다.  예를 들어, "웹 사이트"입니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 항목 형식에서는 이 특성의 값은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> 속성에 할당하는 값에 해당합니다.  이 특성에 다른 값을 지정할 경우 Visual Studio는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> 속성에서 지정한 동일한 신뢰 수준을 지정하도록 값을 덮어씁니다.|  
|**Type**|필수 **xs:string** 특성입니다.<br /><br /> SharePoint 프로젝트 항목에 대한 식별자입니다.  사용자 지정 SharePoint 프로젝트 항목 형식에서 식별자는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>에 전달하는 문자열입니다.  자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)를 참조하십시오.<br /><br /> Visual Studio에 포함된 기본 제공 SharePoint 프로젝트 항목을 위한 식별자 목록은 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)을 참조하십시오.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|선택적 요소입니다.<br /><br /> SharePoint 프로젝트 항목과 연결된 사용자 지정 데이터 항목의 컬렉션을 나타냅니다.<br /><br /> **ExtensionData** 요소가 하나만 포함될 수 있습니다.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|선택적 요소입니다.<br /><br /> SharePoint에 배포될 때 기능과 함께 포함된 속성 값의 컬렉션을 나타냅니다.<br /><br /> **FeatureProperties** 요소가 하나만 포함될 수 있습니다.|  
|[Files](../sharepoint/files-element.md)|선택적 **FileCollectionType** 요소입니다.<br /><br /> Feature 요소 파일 및 종속된 비 SharePoint 프로젝트 출력 등, SharePoint 프로젝트 항목과 함께 배포할 파일을 지정합니다.<br /><br /> **Files** 또는 **ProjectItemFolder** 요소를 둘 모두가 아닌 하나만 포함해야 합니다.|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|선택적 **ProjectItemFolderType** 요소입니다.<br /><br /> 매핑된 폴더를 나타냅니다.<br /><br /> **Files** 또는 **ProjectItemFolder** 요소를 둘 모두가 아닌 하나만 포함해야 합니다.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|선택적 요소입니다.<br /><br /> 사용자가 SharePoint 사이트의 모든 ASPX 페이지에서 액세스하는 데 안전한 것으로 지정된 ASPX 컨트롤 또는 웹 파트의 컬렉션을 나타냅니다.<br /><br /> **SafeControls** 요소가 하나만 포함될 수 있습니다.|  
  
### 부모 요소  
 없음  
  
## 요소 정보  
  
|||  
|-|-|  
|**Namespace**|http:\/\/schemas.microsoft.com\/VisualStudio\/2010\/SharePointTools\/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비워 둘 수 있습니다.**|아니요|  
  
## 참고 항목  
 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  