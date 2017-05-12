---
title: "기능 및 패키지 매니페스트에서 XML 병합"
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
  - "Visual Studio에서 SharePoint 개발, 패키징"
ms.assetid: fc1cbd2a-0166-4f2f-a81b-4dac2fa7b0f3
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 기능 및 패키지 매니페스트에서 XML 병합
  기능과 패키지는 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일에서 정의됩니다.  이러한 패키지된 매니페스트는 디자이너에서 생성된 데이터와 사용자가 매니페스트 템플릿에 입력한 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]의 조합입니다.  패키징 시에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 문과 디자이너 제공 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]을 병합하여 패키지된 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일을 생성합니다.  파일을 SharePoint에 배포한 후 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 유효성 검사 오류를 방지하고 매니페스트 파일을 더 작고 효율적으로 만들기 위해 유사한 요소가 병합됩니다. 이때 뒷부분의 병합 예외에 나와 있는 요소는 제외됩니다.  
  
## 매니페스트 수정  
 기능 또는 패키지 디자이너를 사용하지 않도록 설정할 때까지 패키지된 매니페스트 파일을 직접 수정할 수 없습니다.  그러나 기능 및 패키지 디자이너나 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 편집기를 통해 매니페스트 템플릿에 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소를 수동으로 추가할 수 있습니다.  자세한 내용은 [방법: SharePoint 기능 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md) 및 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)를 참조하십시오.  
  
## 기능 및 패키지 매니페스트 병합 프로세스  
 사용자 지정 요소를 디자이너 제공 요소와 함께 결합할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 다음 프로세스를 사용합니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 각 요소에 고유한 키 값이 있는지 확인합니다.  요소에 고유 키 값이 없을 경우, 패키징된 매니페스트 파일에 추가 됩니다.  마찬가지로, 여러 키를 가지는 요소들은 병합될 수 없습니다.  매니페스트 파일에 추가됩니다.  
  
 요소에 고유 키가 있는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 디자이너 키와 사용자 지정 키의 값을 비교합니다.  두 값이 일치하면 한 값으로 병합되고,  두 값이 다르면 디자이너 키 값이 삭제되고 사용자 지정 키 값이 사용됩니다.  또한 컬렉션도 병합됩니다.  예를 들어, 디자이너에서 생성된 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]과 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]에 Assemblies 컬렉션이 포함된 경우 패키지된 매니페스트에는 Assemblies 컬렉션이 하나만 포함됩니다.  
  
## 병합 예외  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 대부분의 디자이너 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소를 유사한 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소와 함께 병합합니다. 이때 병합되는 요소는 고유한 단일 식별 특성을 갖고 있어야 합니다.  그러나 일부 요소에는 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 병합에 필요한 고유 식별자가 없습니다.  이러한 요소를 *병합 예외*라고 합니다.  이러한 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소를 디자이너 제공 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 요소와 함께 병합하지 않고 대신 패키지된 매니페스트 파일에 추가합니다.  
  
 기능 및 패키지 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 매니페스트 파일의 병합 예외 목록은 다음과 같습니다.  
  
|디자이너|XML 요소|  
|----------|------------|  
|기능 디자이너|ActivationDependency|  
|기능 디자이너|UpgradeAction|  
|패키지 디자이너|SafeControl|  
|패키지 디자이너|CodeAccessSecurity|  
  
## 기능 매니페스트 요소  
 다음 표에는 병합될 수 있는 모든 기능 매니페스트 요소의 목록과 일치에 사용되는 요소의 고유 키가 나와 있습니다.  
  
|요소 이름|고유 키|  
|-----------|----------|  
|Feature\(모든 특성\)|*Attribute Name* \(Feature 요소의 각 특성 이름이 고유 키임\)|  
|ElementFile|위치|  
|ElementManifests\/ElementManifest|위치|  
|Properties\/Property|Key|  
|CustomUpgradeAction|Name|  
|CustomUpgradeActionParameter|Name|  
  
> [!NOTE]  
>  CustomUpgradeAction 요소는 사용자 지정 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 편집기에서만 수정할 수 있기 때문에 병합하지 않는 경우의 효과가 낮습니다.  
  
## 패키지 매니페스트 요소  
 다음 표에는 병합될 수 있는 모든 패키지 매니페스트 요소의 목록과 일치에 사용되는 요소의 고유 키가 나와 있습니다.  
  
|요소 이름|고유 키|  
|-----------|----------|  
|Solution\(모든 특성\)|*Attribute Name* \(Solution 요소의 각 특성 이름이 고유 키임\)|  
|ApplicationResourceFiles\/ApplicationResourceFile|위치|  
|Assemblies\/Assembly|위치|  
|ClassResources\/ClassResource|위치|  
|DwpFiles\/DwpFile|위치|  
|FeatureManifests\/FeatureManifest|위치|  
|Resources\/Resource|위치|  
|RootFiles\/RootFile|위치|  
|SiteDefinitionManifests\/SiteDefinitionManifest|위치|  
|WebTempFile|위치|  
|TemplateFiles\/TemplateFile|위치|  
|SolutionDependency|솔루션 ID|  
  
## 배포된 파일 수동 추가  
 ApplicationResourceFile 및 DwpFiles와 같은 일부 매니페스트 요소는 파일 이름이 포함된 위치를 지정합니다.  그러나 파일 이름 항목을 매니페스트 템플릿에 추가하는 경우 기본 파일이 패키지에 추가되지 않습니다.  따라서 기본 파일을 프로젝트에 직접 추가하여 패키지에 포함하고 배포 형식 속성을 적절하게 설정해야 합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  