---
title: "프로젝트 항목에 패키징 및 배포 정보 제공 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.Project.SafeControlEntries"
  - "VS.SharePointTools.Project.ProjectOutputReference"
  - "VS.SharePointTools.Project.FeatureProperties"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "기능 속성[Visual Studio에서 SharePoint 개발]"
  - "기능 수신자[Visual Studio에서 SharePoint 개발]"
  - "프로젝트 출력 참조[Visual Studio에서 SharePoint 개발]"
  - "안전 컨트롤[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 고급 패키징 도구"
  - "Visual Studio에서 SharePoint 개발, 기능 속성"
  - "Visual Studio에서 SharePoint 개발, 기능 수신자"
  - "Visual Studio에서 SharePoint 개발, 프로젝트 출력 참조"
  - "Visual Studio에서 SharePoint 개발, 안전 컨트롤"
ms.assetid: 209ff3b9-d701-4d27-9d24-005fcc811cbe
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 프로젝트 항목에 패키징 및 배포 정보 제공
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 모든 SharePoint 프로젝트 항목에는 프로젝트가 SharePoint에 배포될 때 추가 데이터를 제공하는 데 사용할 수 있는 속성이 있습니다.  속성은 다음과 같습니다.  
  
-   기능 속성  
  
-   기능 수신기  
  
-   프로젝트 출력 참조  
  
-   안전 컨트롤 항목  
  
 이러한 속성은 **속성** 창에 나타납니다.  
  
## 기능 속성  
 **기능 속성** 속성을 사용하여 기능에서 사용하는 데이터를 지정할 수 있습니다.  기능 속성 데이터는 기능이 SharePoint에 배포될 때 기능과 함께 포함된 값\(키\/값 쌍으로 저장됨\)의 집합입니다.  기능이 배포된 후 코드에서 기능의 속성 값에 액세스할 수 있습니다.  
  
 기능 속성 값을 프로젝트 항목에 추가하면 이 값이 항목의 기능에 대한 매니페스트에서 요소로 추가됩니다.  예를 들어, BDC\(비즈니스 데이터 연결\) 모델 프로젝트에서 ModelFileName 기능 속성은 다음과 같이 나타납니다.  
  
```  
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />   
```  
  
 기능 속성 값을 설정하면 이 값이 프로젝트의 .spdata 파일에서 FeatureProperty 요소로 추가됩니다.  SharePoint에서 속성에 액세스하는 방법에 대한 자세한 내용은 [SPFeaturePropertyCollection Class](http://go.microsoft.com/fwlink/?LinkId=177391) 를 참조하십시오.  
  
 모든 프로젝트 항목의 동일한 기능 속성 값이 기능 매니페스트에 함께 병합됩니다.  그러나 서로 다른 두 프로젝트 항목이 일치하지 않는 값을 사용하여 동일한 기능 속성 키를 지정하는 경우 유효성 검사 오류가 발생합니다.  
  
 기능 속성을 기능 파일\(\*.feature\)에 직접 추가하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 개체 모델 메서드 <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A>를 호출합니다.  이 메서드를 사용하는 경우 기능 속성에서 동일한 기능 속성 값을 추가하는 데 대한 동일한 규칙이 기능 파일에 직접 추가된 속성에도 적용됩니다.  
  
## 기능 수신기  
 기능 수신기는 프로젝트 항목의 포함하는 기능에 특정 이벤트가 발생하면 실행되는 코드입니다.  예를 들어, 기능이 설치되거나, 활성화되거나, 업그레이드되면 실행되는 기능 수신기를 정의할 수 있습니다.  기능 수신기를 추가하는 한 가지 방법은 [연습: 기능 이벤트 수신자 추가](../sharepoint/walkthrough-add-feature-event-receivers.md)에 설명된 대로 기능에 직접 추가하는 것입니다.  다른 방법은 **기능 수신기** 속성에서 기능 수신기 클래스 이름 및 어셈블리를 참조하는 것입니다.  
  
### 직접 메서드  
 기능 수신기를 기능에 직접 추가하면 코드 파일이 솔루션 탐색기의 **기능** 노드 아래에 배치됩니다.  SharePoint 솔루션을 빌드하면 코드가 어셈블리로 컴파일되고 SharePoint에 배포됩니다.  기본적으로 **수신기 어셈블리** 및 **수신기 클래스** 기능 속성은 클래스 이름 및 어셈블리를 참조합니다.  
  
### 참조 메서드  
 기능 수신기를 추가하는 또 다른 방법은 프로젝트 항목의 **기능 수신기** 속성을 사용하여 기능 수신기 어셈블리를 참조하는 것입니다.  기능 수신기 속성 값에는 두 가지 하위 속성인 **어셈블리** 및 **클래스 이름**이 있습니다.  어셈블리는 정규화된 "강력한" 이름을 사용해야 하며 클래스 이름은 전체 형식 이름이어야 합니다.  자세한 내용은 [강력한 이름의 어셈블리](http://go.microsoft.com/fwlink/?LinkID=169573) 를 참조하십시오.  솔루션을 SharePoint에 배포한 후 기능은 참조된 기능 수신기를 사용하여 기능 이벤트를 처리합니다.  
  
 솔루션 빌드 시에 기능과 해당 프로젝트의 기능 수신기 속성 값은 함께 병합되어 SharePoint 솔루션 파일\(.wsp\)의 기능 매니페스트에서 Feature 요소의 ReceiverAssembly 및 ReceiverClass 특성을 설정합니다.  따라서 프로젝트 항목과 기능의 어셈블리 및 클래스 이름 속성 값이 모두 지정된 경우 프로젝트 항목 및 기능 속성 값이 일치해야 합니다.  이러한 값이 일치하지 않으면 유효성 검사 오류가 발생합니다.  프로젝트 항목이 해당 기능에서 사용하는 것이 아닌 기능 수신기 어셈블리를 참조하도록 하려면 프로젝트 항목을 다른 기능으로 이동합니다.  
  
 서버에 없는 기능 수신기 어셈블리를 참조하는 경우 해당 어셈블리 파일을 패키지에 포함해야 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 기능 수신기 어셈블리를 자동으로 추가하지 않습니다.  기능을 배포할 때 어셈블리 파일은 시스템의 [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] 또는 SharePoint 실제 디렉터리의 Bin 폴더에 복사됩니다.  자세한 내용은 [방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)를 참조하십시오.  
  
 기능 수신기에 대한 자세한 내용은 [기능 이벤트 수신기](http://go.microsoft.com/fwlink/?LinkID=169574) 및 [기능 이벤트](http://go.microsoft.com/fwlink/?LinkID=169575) 를 참조하십시오.  
  
## 프로젝트 출력 참조  
 프로젝트 출력 참조 속성은 프로젝트 항목이 실행해야 하는 어셈블리 등의 종속성을 지정합니다.  예를 들어, 솔루션에 BDC 프로젝트와 클래스 프로젝트가 있는 경우  BDC 프로젝트가 클래스 프로젝트에서 출력하는 어셈블리에 종속되어 있으면 BDC 프로젝트의 프로젝트 출력 참조 속성에서 어셈블리를 참조할 수 있습니다.  BDC 프로젝트가 패키지되는 경우 종속 어셈블리가 패키지에 포함됩니다.  
  
 프로젝트 출력 참조는 대개 어셈블리이지만 Silverlight 프로젝트와 같은 경우에는 다른 파일 형식일 수 있습니다.  
  
 자세한 내용은 [방법: 프로젝트 출력 참조 추가](../sharepoint/how-to-add-a-project-output-reference.md)을 참조하십시오.  
  
## 안전 컨트롤 항목  
 SharePoint에서는 안전 컨트롤 항목이라는 보안 메커니즘을 제공하여 신뢰할 수 없는 사용자가 특정 컨트롤에만 액세스하도록 제한합니다.  SharePoint는 신뢰할 수 없는 사용자가 SharePoint 서버에서 ASPX 페이지를 업로드하고 만들 수 있도록 디자인되었습니다.  이러한 사용자가 안전하지 않은 코드를 ASPX 페이지에 추가하는 것을 방지하기 위해 SharePoint에서는 이러한 사용자가 *안전 컨트롤*에만 액세스하도록 제한합니다.  안전 컨트롤은 안전한 것으로 지정되었으며 사이트의 모든 사용자가 사용할 수 있는 ASPX 컨트롤 및 웹 파트입니다.  자세한 내용은 [4 단계: 안전한 컨트롤 목록에 웹 파트 추가](http://go.microsoft.com/fwlink/?LinkID=171014) 를 참조하십시오.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 모든 SharePoint 프로젝트 항목은 부울 하위속성인 **안전** 및 **스크립트에 대해 안전** 을 가지는 **안전 컨트롤 항목** 속성을 가집니다.  안전 속성은 신뢰할 수 없는 사용자가 컨트롤에 액세스할 수 있는지 여부를 지정 합니다.  스크립트에 대해 안전 속성은 신뢰할 수 없는 사용자가 컨트롤의 속성을 보고 변경할 수 있는지 여부를 지정합니다.  
  
 안전 컨트롤 항목은 어셈블리를 기준으로 참조됩니다.  안전 컨트롤 항목을 프로젝트 항목의 **안전 컨트롤 항목** 속성에서 입력하여 프로젝트의 어셈블리에 추가할 수 있습니다.  그러나 추가 어셈블리를 패키지에 추가할 때 **패키지 디자이너**의 **고급** 탭을 통해 프로젝트의 어셈블리에 안전 컨트롤 항목을 추가할 수도 있습니다.  자세한 내용은 [방법: 컨트롤을 안전 컨트롤로 표시](../sharepoint/how-to-mark-controls-as-safe-controls.md) 또는 [웹 파트 어셈블리를 안전한 컨트롤로 등록](http://go.microsoft.com/fwlink/?LinkID=171013) 을 참조하십시오.  
  
### 안전 컨트롤의 XML 항목  
 안전 컨트롤 항목을 프로젝트 항목이나 프로젝트의 어셈블리에 추가할 때 참조가 패키지 매니페스트에 다음 형식으로 기록됩니다.  
  
```  
<Assemblies>  
    <Assembly Location="<assembly name>.dll"     
      DeploymentTarget="<'GlobalAssemblyCache' or 'WebApplication'">>  
        <SafeControls>  
            <SafeControl Assembly="<assembly name>.dll" Namespace=  
              "<SharePoint project name>" Safe="<true/false>"     
                TypeName="<control name>"   
                SafeAgainstScript="<true/false>" />  
        </SafeControls>  
    </Assembly>  
</Assemblies>  
```  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md)   
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  