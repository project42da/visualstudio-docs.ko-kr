---
title: "Overview of the Programming Model of SharePoint Tools Extensions | Microsoft Docs"
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
  - "Visual Studio, extending tools"
  - "SharePoint development in Visual Studio, extensibility object models"
  - "SharePoint development in Visual Studio, extending tools"
ms.assetid: aec8165b-dff9-47be-82a5-3fa38e579297
caps.latest.revision: 55
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 54
---
# Overview of the Programming Model of SharePoint Tools Extensions
  Visual Studio에서 SharePoint 도구의 확장을 만드는 경우 SharePoint 도구에서 노출하는 확장성 인터페이스를 하나 이상 구현하여 시작합니다.  대부분의 경우 SharePoint 도구에서 제공하는 다른 형식을 사용하여 확장에서 기능도 구현합니다.  일부 시나리오에서는 Visual Studio 및 SharePoint에서 제공하는 다른 개체 모델의 형식을 사용할 수도 있습니다.  이러한 각 개체 모델의 용도를 이해하고 이러한 개체 모델을 서로 사용하여 SharePoint 도구의 확장을 만드는 방법을 알아야 합니다.  
  
## 확장성 인터페이스를 구현하여 SharePoint 도구 확장  
 Visual Studio에서는 .NET Framework 4의 MEF\(Managed Extensibility Framework\)를 사용하여 SharePoint 도구에 대한 확장성 모델을 제공합니다.  MEF는 System.ComponentModel.Composition 어셈블리에서 구현된 API로, 응용 프로그램에서 확장성 지점을 노출하고 런타임에 확장을 검색하고 로드할 수 있도록 합니다.  MEF에 대한 자세한 내용은 [MEF&#40;Managed Extensibility Framework&#41;](../Topic/Managed%20Extensibility%20Framework%20(MEF).md)를 참조하세요.  
  
 SharePoint 도구를 확장하려면 Visual Studio에서 노출하는 확장성 인터페이스를 하나 이상 구현합니다.  또한 <xref:System.ComponentModel.Composition.ExportAttribute>와 필요에 따라 추가 SharePoint 도구 관련 특성을 인터페이스 구현에 적용해야 합니다.  다음 표에는 SharePoint 도구를 확장하기 위해 구현할 수 있는 인터페이스가 나와 있습니다.  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider>|새 형식의 SharePoint 프로젝트 항목을 정의하려면 이 인터페이스를 구현합니다.  예제는 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)를 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension>|Visual Studio에 이미 설치되어 있는 SharePoint 프로젝트 항목의 형식을 확장하려면 이 인터페이스를 구현합니다.  예제는 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)를 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension>|SharePoint 프로젝트를 확장하려면 이 인터페이스를 구현합니다.  예제는 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)를 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep>|SharePoint 프로젝트 항목이 배포되거나 취소될 때 실행할 수 있는 새로운 배포 단계를 정의하려면 이 인터페이스를 구현합니다.  예제는 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)를 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension>|**서버 탐색기** 창의 **SharePoint 연결** 노드 아래에 있는 기존 노드를 확장하려면 이 인터페이스를 구현합니다.  예제는 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider>|**서버 탐색기** 창의 **SharePoint 연결** 노드 아래에 새로운 형식의 노드를 정의하려면 이 인터페이스를 구현합니다.  예제는 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule>|사용자 지정 기능 유효성 검사 규칙을 정의하려면 이 인터페이스를 구현합니다.  예제는 [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)를 참조하세요.|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule>|사용자 지정 패키지 유효성 검사 규칙을 정의하려면 이 인터페이스를 구현합니다.  예제는 [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)를 참조하세요.|  
  
 SharePoint 도구의 확장을 구현한 후에는 VSIX\(Visual Studio Extension\) 패키지의 확장 어셈블리를 배포하여 Visual Studio에서 확장을 검색하고 로드할 수 있도록 합니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하세요.  
  
## SharePoint 도구 확장에서 사용하는 개체 모델 이해  
 SharePoint 도구의 확장을 만들 때 사용할 수 있는 몇 가지 개체 모델은 다음과 같습니다.  
  
-   *SharePoint 도구 개체 모델*.  이 개체 모델에서는 SharePoint 도구 확장과 기타 관련 형식을 만들기 위해 구현하는 확장성 인터페이스를 제공합니다.  
  
-   *Visual Studio 자동화 및 통합 개체 모델*.  이러한 개체 모델을 사용하여 SharePoint 도구 개체 모델의 범위를 벗어나는 Visual Studio 기능에 액세스할 수 있습니다.  
  
    > [!NOTE]  
    >  SharePoint 프로젝트 서비스를 사용하여 SharePoint 도구 개체 모델의 일부 개체를 Visual Studio 자동화 및 통합 개체 모델의 개체로 변환하거나 그 반대로 변환할 수 있습니다.  자세한 내용은 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)을 참조하세요.  
  
-   *SharePoint 서버 및 클라이언트 개체 모델*.  이러한 개체 모델을 사용하여 SharePoint 사이트를 수정하여 SharePoint 도구 확장의 컨텍스트에서 SharePoint 사이트의 데이터를 검색할 수 있습니다.  
  
### SharePoint 도구 개체 모델  
 각 SharePoint 도구 확장에서는 SharePoint 도구 개체 모델의 형식을 사용하여 확장의 핵심 동작 및 기능을 정의합니다.  다음 표에서는 이 개체 모델에 포함된 네임스페이스에 대해 설명합니다.  
  
|어셈블리|네임스페이스|설명|  
|----------|------------|--------|  
|Microsoft.VisualStudio.SharePoint.dll|<xref:Microsoft.VisualStudio.SharePoint>|SharePoint 프로젝트 시스템을 확장하고 자동화하는 데 사용하는 형식을 포함합니다.  예를 들어 기본 제공 SharePoint 프로젝트 및 프로젝트 항목을 확장하거나, 고유한 프로젝트 항목을 만들 수 있습니다.  자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하세요.|  
||<xref:Microsoft.VisualStudio.SharePoint.Deployment>|사용자 고유의 배포 단계 및 배포 구성을 만드는 등 SharePoint 프로젝트에 대한 배포 프로세스를 확장하는 데 사용하는 형식을 포함합니다.  자세한 내용은 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)을 참조하세요.|  
||<xref:Microsoft.VisualStudio.SharePoint.Explorer>|**서버 탐색기** 창의 **SharePoint 연결** 노드 아래에 있는 노드를 확장하고 새로운 형식의 노드를 정의하는 데 사용하는 형식을 포함합니다.  자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하세요.|  
||<xref:Microsoft.VisualStudio.SharePoint.Features>|SharePoint 프로젝트의 기능 정의에 액세스하는 데 사용되는 형식을 포함합니다.|  
||<xref:Microsoft.VisualStudio.SharePoint.Packages>|SharePoint 솔루션의 패키지 정의에 액세스하는 데 사용되는 형식을 포함합니다.|  
||<xref:Microsoft.VisualStudio.SharePoint.Validation>|SharePoint 프로젝트의 기능 및 패키지 유효성 검사 동작을 사용자 지정하는 데 사용되는 형식을 포함합니다.  자세한 내용은 [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)를 참조하세요.|  
|Microsoft.VisualStudio.SharePoint.Commands.dll|<xref:Microsoft.VisualStudio.SharePoint.Commands>|사용자 지정 *SharePoint 명령*을 만드는 데 사용할 수 있는 형식을 포함합니다.  SharePoint 명령은 SharePoint 도구 확장에서 SharePoint 서버 개체 모델을 호출하는 메서드입니다.  자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하세요.|  
|Microsoft.VisualStudio.SharePoint.Explorer.Extensions.dll|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions>|SharePoint 사이트의 개별 구성 요소를 나타내는 기본 제공 **서버 탐색기** 노드\(예: 목록, 필드 또는 콘텐츠 형식을 나타내는 노드\)에 대한 정보를 가져오는 데 사용할 수 있는 형식을 포함합니다.  자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하세요.|  
  
### Visual Studio 자동화 개체 모델  
 Visual Studio 자동화 개체 모델은 Visual Studio 프로젝트와 IDE를 자동화하는 데 사용할 수 있는 API를 제공합니다.  Visual Studio 개체 모델을 사용하면 SharePoint 프로젝트에 한정되지 않는 프로젝트 관련 작업을 수행하거나 Visual Studio에서 기타 일반적인 자동화 작업을 수행할 수 있습니다.  이 개체 모델은 일반적으로 Visual Studio 추가 기능 및 매크로에 많이 사용하지만 Sharepoint 도구 확장에 사용할 수도 있습니다.  
  
 Visual Studio 자동화 개체 모델의 주요 부분은 EnvDTE.dll 어셈블리에서 정의됩니다.  EnvDTE80.dll, EnvDTE90.dll, EnvDTE100.dll 및 EnvDTE110.dll 어셈블리는 각각 Visual Studio 2005, Visual Studio 2008, Visual Studio 2010 및 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)]에 도입된 추가 기능을 제공하며,  Visual Studio에 포함되어 있습니다.  
  
 자동화 개체 모델에 대한 자세한 내용은 [Extending the Visual Studio Environment](../Topic/Extending%20the%20Visual%20Studio%20Environment.md) 및 [Automation and Extensibility Reference](../Topic/Automation%20and%20Extensibility%20Reference.md)를 참조하세요.  
  
### Visual Studio 통합 개체 모델  
 통합 개체 모델에서는 *VSPackage*를 만들어 Visual Studio에 기능을 추가하는 데 사용할 수 있는 API를 제공합니다.  VSPackage는 도구 창, 편집기, 디자이너, 서비스, 프로젝트 등의 사용자 지정 기능을 제공하여 Visual Studio IDE를 확장하는 모듈입니다.  
  
 기본 제공 SharePoint 도구와 함께 사용할 새 Visual Studio 기능을 추가하려는 경우 통합 개체 모델을 사용할 수 있습니다.  예를 들어 SharePoint 사이트에 대한 사용자 지정 작업을 나타내는 사용자 지정 SharePoint 프로젝트 항목을 만드는 경우 사용자 지정 작업용 디자이너를 구현하는 VSPackage를 만들 수도 있습니다.  **솔루션 탐색기**에서 사용자 지정 작업을 나타내는 프로젝트 항목에 바로 가기 메뉴 항목을 추가하여 디자이너를 사용자 지정 작업에 연결할 수 있습니다.  사용자 지정 작업 프로젝트를 마우스 오른쪽 단추로 클릭하거나, 이 프로젝트를 선택한 다음 Shift\+F10을 선택하여 해당 바로 가기 메뉴를 열고 **열기**를 선택하여 디자이너를 열 수 있습니다.  
  
 이 개체 모델은 Visual Studio SDK에 포함된 어셈블리 집합에서 정의됩니다.  이 개체 모델의 일부 주 어셈블리에는 Microsoft.VisualStudio.Shell.11.0.dll, Microsoft.VisualStudio.Shell.Interop.dll 및 Microsoft.VisualStudio.OLE.Interop.dll이 포함되어 있습니다.  
  
 통합 개체 모델에 대한 자세한 내용은 [Visual Studio 확장성 아키텍처](/visual-cpp/misc/visual-studio-extensibility-architecture) 및 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)를 참조하세요.  
  
### SharePoint 개체 모델  
 SharePoint 도구 확장에서는 SharePoint API를 사용하여 SharePoint 사이트를 수정하거나 SharePoint 사이트에서 데이터를 검색할 수 있습니다.  [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]에서는 두 가지 개체 모델인 서버 개체 모델과 클라이언트 개체 모델을 제공합니다.  
  
 SharePoint 도구 확장에서 두 개체 모델의 API를 모두 사용할 수 있지만 SharePoint 도구 확장의 컨텍스트에서 각 개체 모델에 장단점이 있습니다.  자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하세요.  
  
|개체 모델|설명|  
|-----------|--------|  
|서버 개체 모델|서버 개체 모델을 사용하면 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]에 표시되는 모든 기능을 프로그래밍 방식으로 액세스할 수 있습니다.  이 개체 모델은 SharePoint 서버에서 실행되는 SharePoint 솔루션에 사용됩니다.  이 개체 모델은 대부분 Microsoft.SharePoint.dll 어셈블리에서 정의됩니다.  서버 개체 모델에 대한 자세한 내용은 [SharePoint Foundation Server 쪽 개체 모델 사용](http://go.microsoft.com/fwlink/?LinkId=177796)을 참조하세요.|  
|클라이언트 개체 모델|클라이언트 개체 모델은 원격 클라이언트나 서버의 SharePoint 데이터와 상호 작용하는 데 사용할 수 있는 서버 개체 모델의 하위 집합입니다.  이 모델은 일반적인 작업을 수행하기 위해 실행해야 하는 왕복 수를 최소화하도록 디자인되었습니다.  클라이언트 개체 모델은 대부분 Microsoft.SharePoint.Client.dll 및 Microsoft.SharePoint.Client.Runtime.dll 어셈블리에서 정의됩니다.  클라이언트 개체 모델에 대한 자세한 내용은 [관리되는 클라이언트 개체 모델](http://go.microsoft.com/fwlink/?LinkId=177797)을 참조하세요.|  
  
## 참고 항목  
 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)  
  
  