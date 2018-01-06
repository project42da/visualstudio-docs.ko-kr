---
title: "패키지 및 프로젝트 항목에 대 한 배포 정보 제공 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.SafeControlEntries
- VS.SharePointTools.Project.ProjectOutputReference
- VS.SharePointTools.Project.FeatureProperties
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature properties
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
- feature properties [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature receiver
- feature receiver [SharePoint development in Visual Studio]
- safe controls [SharePoint development in Visual Studio]
ms.assetid: 209ff3b9-d701-4d27-9d24-005fcc811cbe
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 84379f4847bb708bf8089ac32e261b459e87e1a1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="providing-packaging-and-deployment-information-in-project-items"></a>Providing Packaging and Deployment Information in Project Items
  모든 SharePoint 프로젝트 항목 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트는 SharePoint에 배포 될 때 추가 데이터를 제공 하는 데 사용할 수 있는 속성이 있습니다. 속성은 다음과 같습니다.  
  
-   기능 속성  
  
-   기능 수신자  
  
-   프로젝트 출력 참조  
  
-   안전 컨트롤 항목  
  
 이러한 속성에 표시 된 **속성** 창.  
  
## <a name="feature-properties"></a>기능 속성  
 사용 하 여는 **기능 속성** 속성을 사용 하는 데이터를 지정 합니다. 기능 속성 데이터는 SharePoint에 배포 될 때 기능과 함께 제공 되는 값 (키/값 쌍으로 저장 됨)의 집합입니다. 기능이 배포되고 나서 코드에서 속성 값에 액세스할 수 있습니다.  
  
 기능 속성 값은 프로젝트 항목에 추가 하면 항목의 기능 매니페스트에 요소 값이 추가 됩니다. BDC 비즈니스 데이터 연결 () 모델 프로젝트에서 예를 들어 ModelFileName 기능 속성 다음과 같이 표시 됩니다.  
  
```  
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />   
```  
  
 기능 속성 값을 설정 하면 프로젝트의.spdata 파일에서 FeatureProperty 요소로 추가 됩니다. SharePoint에서 속성에 액세스 하는 방법에 대 한 정보를 참조 하십시오. [SPFeaturePropertyCollection 클래스](http://go.microsoft.com/fwlink/?LinkId=177391)합니다.  
  
 기능 매니페스트에 모든 프로젝트 항목의 동일한 기능 속성 값은 함께 병합 됩니다. 그러나 값이 일치 하지 않는 동일한 기능 속성 키를 지정 하는 두 개의 서로 다른 프로젝트 항목, 유효성 검사 오류가 발생 합니다.  
  
 기능 속성 기능 파일을 직접 추가할 수 (*.feature)를 호출 하는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 개체 모델 메서드 <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A>합니다. 이 메서드를 사용 하는 경우 동일한 규칙이 기능 속성에 동일한 기능 속성 값을 추가 하는 방법에 대 한 기능 파일에 직접 추가 된 속성에도 적용 되도록 주의 해야 합니다.  
  
## <a name="feature-receiver"></a>기능 수신기  
 기능 수신기는 프로젝트 항목에 특정 이벤트가 발생할 때 실행 되는 코드의 기능을 포함 합니다. 예를 들어 기능 설치, 활성화 또는 업그레이드할 때 실행 되는 기능 수신기를 정의할 수 있습니다. 에 설명 된 대로 기능에 직접 추가 하는 기능 수신기를 추가 하는 한 가지 방법은 [연습: 기능 이벤트 수신자 추가](../sharepoint/walkthrough-add-feature-event-receivers.md)합니다. 기능 수신기 클래스 이름 및 어셈블리에서 참조 하는 또 다른 방법은 **기능 수신기** 속성입니다.  
  
### <a name="direct-method"></a>직접적인 방법  
 아래 기능에 직접 기능 수신기를 추가할 때 코드 파일에 저장 됩니다는 **기능** 솔루션 탐색기에서 노드. SharePoint 솔루션을 빌드할 때 코드를 어셈블리로 컴파일하고 SharePoint에 배포 합니다. 기본적으로 기능 속성 **수신기 어셈블리** 및 **수신기 클래스** 클래스 이름 및 어셈블리 참조입니다.  
  
### <a name="reference-method"></a>Reference 메서드  
 기능 수신기를 추가 하 여를 사용 하 여 **기능 수신기** 기능 수신기 어셈블리를 참조 하는 프로젝트 항목의 속성입니다. 기능 수신기 속성 값에 두 개의 하위: **어셈블리** 및 **클래스 이름**합니다. 정규화 된 어셈블리를 사용해선, "강력한" 이름과 클래스 이름에는 전체 유형 이름 이어야 합니다. 자세한 내용은 [강력한 이름의 어셈블리](http://go.microsoft.com/fwlink/?LinkID=169573)를 참조하세요. SharePoint 솔루션에 배포한 후 기능 기능 이벤트를 처리 하는 참조 된 기능 수신기를 사용 합니다.  
  
 솔루션 빌드 시 기능 및 해당 프로젝트의 기능 수신기 속성 값을 함께 병합할 SharePoint 솔루션 (.wsp) 파일의 기능 매니페스트에 기능 요소의 ReceiverAssembly 및 ReceiverClass 속성을 설정 하려면. 따라서 프로젝트 항목 및 기능의 어셈블리 및 클래스 이름 속성 값 둘 다 지정 프로젝트 항목 및 기능 속성 값이 일치 해야 합니다. 값이 일치 하지 않는 경우 유효성 검사 오류를 받게 됩니다. 프로젝트 항목을 하려는 경우 해당 기능은 이외의 다른 기능 수신기 어셈블리 참조를 사용 하 여, 다른 기능으로 이동 합니다.  
  
 패키지에 어셈블리 파일 자체 포함 해야 하는 서버에 설치 되지 않은 기능 수신기 어셈블리를 참조 하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 를 추가 하지 않습니다. 시스템의 어셈블리 파일이 복사 된 기능을 배포 하는 경우 [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] 또는 SharePoint 실제 디렉터리의 Bin 폴더입니다. 자세한 내용은 참조 하는 방법: [하는 방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)합니다.  
  
 기능 수신기에 대 한 자세한 내용은 참조 [기능 이벤트 수신기](http://go.microsoft.com/fwlink/?LinkID=169574) 및 [기능 이벤트](http://go.microsoft.com/fwlink/?LinkID=169575)합니다.  
  
## <a name="project-output-references"></a>프로젝트 출력 참조  
 프로젝트 출력 참조 속성에는 프로젝트 항목을 실행 해야 하는 어셈블리 등의 종속성을 지정 합니다. 예를 들어, BDC 프로젝트 및 클래스 프로젝트가 솔루션에 포함 합니다. BDC 프로젝트 클래스 프로젝트에서 출력 하는 어셈블리에 종속 하는 경우에 BDC 프로젝트의 프로젝트 출력 참조 속성에서 해당 어셈블리를 참조할 수 있습니다. BDC 프로젝트가 패키지 되는 경우 패키지에 종속 어셈블리가 포함 됩니다.  
  
 프로젝트 출력 참조는 대개 어셈블리 하지만 일부 경우 (예: Silverlight 프로젝트의 경우) 다른 파일 형식 될 수 있습니다.  
  
 자세한 내용은 참조 [하는 방법: 프로젝트 출력 참조 추가](../sharepoint/how-to-add-a-project-output-reference.md)합니다.  
  
## <a name="safe-control-entries"></a>안전 컨트롤 항목  
 SharePoint에는 특정 컨트롤에 신뢰할 수 없는 사용자의 액세스를 제한 하려면 안전 컨트롤 항목 이라는 보안 메커니즘을 제공 합니다. 기본적으로 SharePoint에는 신뢰할 수 없는 사용자를 업로드 하 여 SharePoint 서버에서 ASPX 페이지를 만들 수 있습니다. 이러한 사용자가 안전 하지 않은 코드 ASPX 페이지를 추가 하지 못하도록 하려면 SharePoint에 대 한 액세스를 제한 *안전 컨트롤*합니다. 안전 컨트롤은 ASPX 컨트롤 및 웹 파트 안전한 것으로 지정 하 고 사이트에서 모든 사용자가 사용할 수 있는 합니다. 자세한 내용은 참조 [4 단계: 안전 컨트롤 목록에 웹 파트 추가](http://go.microsoft.com/fwlink/?LinkID=171014)합니다.  
  
 모든 SharePoint 프로젝트 항목에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 라는 속성이 **안전 컨트롤 항목** 하는 두 가지 부울 하위: **안전** 및 **스크립트에 대해 안전**합니다. 안전 속성은 신뢰할 수 없는 사용자가 컨트롤에 액세스할 수 있는지 여부를 지정합니다. 스크립트에 대해 안전 속성에는 신뢰할 수 없는 사용자가 보고 하 고 컨트롤의 속성을 변경할 수 있는지 여부를 지정 합니다.  
  
 안전 컨트롤 항목은 어셈블리를 기준으로 참조 됩니다. 프로젝트 항목에 입력 하 여 프로젝트의 어셈블리에 안전 컨트롤 항목을 추가할 **안전 컨트롤 항목** 속성입니다. 그러나 추가할 수 있습니다도 안전 컨트롤 항목을 통해 프로젝트의 어셈블리에는 **고급** 탭에 **패키지 디자이너** 패키지에 추가 어셈블리를 추가 하면 합니다. 자세한 내용은 참조 [하는 방법: 안전 컨트롤로 표시 컨트롤](../sharepoint/how-to-mark-controls-as-safe-controls.md) 또는 [웹 파트 어셈블리를 Safe 컨트롤로 등록](http://go.microsoft.com/fwlink/?LinkID=171013)합니다.  
  
### <a name="xml-entries-for-safe-controls"></a>안전 컨트롤에 대 한 XML 항목  
 또는 프로젝트의 어셈블리는 프로젝트 항목에 안전 컨트롤 항목을 추가 하면 다음과 같은 형식의 패키지 매니페스트에 대 한 참조를 기록 됩니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [모듈을 사용 하 여 솔루션의 파일을 포함 하려면](../sharepoint/using-modules-to-include-files-in-the-solution.md)   
 [SharePoint 패키징 및 배포 확장](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  