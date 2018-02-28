---
title: "매니페스트에서 기능 및 패키지 XML 병합 | Microsoft Docs"
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
- SharePoint development in Visual Studio, packaging
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 81e6f83dd4fc825e885843a47d45485918f7dabe
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="merging-xml-in-feature-and-package-manifests"></a>기능 및 패키지 매니페스트에서 XML 병합
  기능과 패키지 정의한 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일. 이러한 패키지에 포함 된 매니페스트는 디자이너와 사용자 지정에서 생성 된 데이터의 조합을 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 템플릿의 사용자가 입력 한 합니다. 패키징 시 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 병합 하는 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 디자이너에서 제공 된 문을 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 하 여 패키지 된 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일. 비슷한 요소 예외 병합의 뒷부분에 설명 된 예외와 병합 됩니다 하지 않으려면 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 보다 작고 효율적인 파일 매니페스트를 확인 하려면 SharePoint에 파일을 배포한 후 유효성 검사 오류입니다.  
  
## <a name="modifying-the-manifests"></a>매니페스트 수정  
 기능 또는 패키지 디자이너를 사용 하지 않도록 설정 될 때까지 직접 패키지에 포함 된 매니페스트 파일은 수정할 수 없습니다. 그러나 사용자 지정 수동으로 추가할 수 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소를 사용 하는 매니페스트 템플릿 기능 및 패키지 디자이너를 통해 또는 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 편집기입니다. 자세한 내용은 참조 [하는 방법: SharePoint 기능을 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md) 및 [하는 방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)합니다.  
  
## <a name="feature-and-package-manifest-merge-process"></a>기능 및 패키지 매니페스트 병합 프로세스  
 디자이너에서 제공 요소와 함께 사용자 지정 요소를 결합 하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 다음 프로세스를 사용 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]각 요소에 고유 키 값이 있는지 여부를 확인 합니다. 요소에 고유한 키 값이 없으면 요소가 패키지된 매니페스트 파일에 추가됩니다. 이와 마찬가지로 여러 키가 있는 요소는 병합될 수 없으므로 따라서 매니페스트 파일에 추가 됩니다.  
  
 요소에 있는 경우 고유 키 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너와 사용자 지정 키의 값을 비교 합니다. 값이 일치 하는 경우 단일 값으로 병합 합니다. 값이 다른 디자이너 키 값이 삭제 되 고 사용자 지정 키 값이 사용 됩니다. 컬렉션도 병합 됩니다. 예를 들어 경우 디자이너에서 생성 된 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 및 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 모두 어셈블리 컬렉션을 포함, 패키지 매니페스트 하나의 어셈블리 컬렉션을 포함 합니다.  
  
## <a name="merge-exceptions"></a>병합 예외  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]대부분의 디자이너 병합 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소와 유사한 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소 단일, 고유한 식별 특성을 갖습니다. 그러나 일부 요소에 필요한 고유 식별자를 부족 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 병합 합니다. 이러한 요소 라고 *병합 예외*합니다. 이러한 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 사용자 지정을 병합 하지 않습니다 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소와 디자이너에서 제공 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소 하지만 대신 패키지 매니페스트 파일에 추가 합니다.  
  
 다음은 기능 및 패키지에 대 한 병합 예외 목록이 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일.  
  
|Designer|XML 요소|  
|--------------|-----------------|  
|기능 디자이너|ActivationDependency|  
|기능 디자이너|UpgradeAction|  
|패키지 디자이너|SafeControl|  
|패키지 디자이너|CodeAccessSecurity|  
  
## <a name="feature-manifest-elements"></a>기능 매니페스트 요소  
 다음 테이블은 병합 될 수 있는 모든 기능 매니페스트 요소 및 일치에 사용 되는 고유 키의 목록입니다.  
  
|요소 이름|고유 키|  
|------------------|----------------|  
|기능 (모든 특성의 경우)|*특성 이름은* (기능 요소는 각 특성 이름에는 고유 키입니다.)|  
|ElementFile|위치|  
|ElementManifests/ElementManifest|위치|  
|속성/속성|Key|  
|CustomUpgradeAction|name|  
|CustomUpgradeActionParameter|name|  
  
> [!NOTE]  
>  사용자 지정 CustomUpgradeAction 요소를 수정 하는 유일한 방법은 중 이므로 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 편집기 병합 되지 않는의 효과 부족 합니다.  
  
## <a name="package-manifest-elements"></a>패키지 매니페스트 요소  
 다음 테이블은 병합 될 수 있는 모든 패키지 매니페스트 요소 및 일치에 사용 되는 고유 키의 목록입니다.  
  
|요소 이름|고유 키|  
|------------------|----------------|  
|솔루션 (모든 특성의 경우)|*특성 이름은* (솔루션 요소는 각 특성 이름에는 고유 키입니다.)|  
|ApplicationResourceFiles/ApplicationResourceFile|위치|  
|어셈블리/어셈블리|위치|  
|ClassResources/ClassResource|위치|  
|DwpFiles/DwpFile|위치|  
|FeatureManifests/FeatureManifest|위치|  
|리소스/리소스|위치|  
|RootFiles/RootFile|위치|  
|SiteDefinitionManifests/SiteDefinitionManifest|위치|  
|WebTempFile|위치|  
|TemplateFiles/TemplateFile|위치|  
|SolutionDependency|SolutionID|  
  
## <a name="manually-add-deployed-files"></a>배포 된 파일을 수동으로 추가  
 ApplicationResourceFile DwpFiles, 등의 몇 가지 매니페스트 요소가 파일 이름을 포함 하는 위치를 지정 합니다. 그러나 추가 파일 이름 항목 매니페스트 서식 파일에 추가 되지 않습니다 내부 파일 패키지에 있습니다. 배포 유형의 속성을 적절 하 게 설정 하 고 패키지에 포함할 프로젝트에 파일을 추가 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  