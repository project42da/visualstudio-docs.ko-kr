---
title: "Creating Item Templates and Project Templates for SharePoint Project Items"
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
  - "SharePoint project items, creating custom templates"
  - ".spdata files"
  - "projects [SharePoint development in Visual Studio], creating custom templates"
  - "SharePoint projects, creating custom templates"
  - "SharePoint development in Visual Studio, creating custom project and item templates"
  - "project items [SharePoint development in Visual Studio], creating custom templates"
ms.assetid: c95b5e35-76c4-4f0a-b645-0467ae683659
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# Creating Item Templates and Project Templates for SharePoint Project Items
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의하는 경우 다른 개발자가 Visual Studio에서 해당 프로젝트 항목을 사용할 수 있도록 이 프로젝트 항목 형식을 항목 템플릿이나 프로젝트 템플릿에 연결할 수 있습니다.  템플릿에 대한 마법사를 만들 수도 있습니다.  
  
 예를 들어 Visual Studio에는 SharePoint 사이트에 필드를 추가하기 위한 프로젝트 템플릿 또는 항목 템플릿이 포함되어 있지 않습니다.  필드를 나타내는 SharePoint 프로젝트 항목 형식을 정의한 다음 다른 개발자가 해당 필드를 SharePoint 프로젝트에 추가하는 데 사용할 수 있는 항목 템플릿을 생성할 수 있습니다.  또는 개발자가 필드 항목이 포함 된 새 SharePoint 프로젝트를 만들 수 있도록 프로젝트 템플릿을 생성할 수 있습니다. 두 경우 모두 개발자가 템플릿을 사용할 때 나타나는 마법사를 제공할 수도 있습니다.  이 마법사는 개발자로부터 정보를 수집하여 새 항목 또는 프로젝트를 구성할 수 있습니다.  
  
 항목 템플릿과 프로젝트 템플릿은 Visual Studio에서 프로젝트 항목이나 프로젝트를 만드는 데 사용하는 파일이 포함된 .zip 파일입니다.  항목 템플릿과 프로젝트 템플릿에 대한 기본적인 내용은 [Visual Studio에서 사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)를 참조하십시오.  
  
##  <a name="creatingitemtemplates"></a> 항목 템플릿 만들기  
 SharePoint 프로젝트 항목에 대한 항목 템플릿을 만드는 경우 항상 필요한 파일과 특정 형식의 프로젝트 항목에서 사용할 수 있는 선택적 파일이 있습니다.  SharePoint 프로젝트 항목 형식을 정의하고 이 형식의 항목 템플릿을 만드는 방법을 보여 주는 연습은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)를 참조하십시오.  
  
 다음 표에는 SharePoint 프로젝트 항목의 항목 템플릿을 만드는 데 필요한 파일이 나와 있습니다.  
  
|필수 파일|설명|  
|-----------|--------|  
|.spdata 파일|프로젝트 항목의 내용과 기본 동작을 지정하는 XML 파일입니다.  이 파일은 항목 템플릿에 포함되어야 합니다.  .spdata 파일의 내용에 대한 자세한 내용은 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)를 참조하십시오.|  
|.vstemplate 파일.|이 파일은 **새 항목 추가** 대화 상자에 템플릿을 표시하고 템플릿에서 프로젝트 항목을 만드는 데 필요한 정보를 Visual Studio에 제공합니다.  이 파일은 항목 템플릿에 포함되어야 합니다.  자세한 내용은 [NIB: Visual Studio Template Metadata Files](http://msdn.microsoft.com/ko-kr/129d59b5-7f9c-4daf-9832-eaedb3c4c961)을 참조하십시오.|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 Visual Studio Extension 어셈블리.|이 어셈블리는 프로젝트 항목의 런타임 동작을 정의합니다.  이 어셈블리는 항목 템플릿이 있는 VSIX 패키지에 포함되어야 합니다.  자세한 내용은 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md) 및 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.|  
  
 다음 표에는 항목 템플릿에 포함될 수 있는 가장 일반적인 선택적 파일이 일부 나와 있습니다.  일부 프로젝트 항목 형식에는 여기에 나와 있지 않은 다른 파일이 필요할 수도 있습니다.  
  
|선택적 파일|설명|  
|------------|--------|  
|Elements.xml|*Feature 요소* 파일입니다.  이 파일에서는 프로젝트 항목에 의해 만들어진 사용자 지정의 UI와 동작을 정의합니다.  목록 인스턴스, 콘텐츠 형식 또는 사용자 지정 작업과 같은 각 사용자 지정 형식에는 이 파일의 내용을 정의하는 각기 다른 스키마가 있습니다.  자세한 내용은 [Building Block: Features](http://go.microsoft.com/fwlink/?LinkId=169183) 및 [Feature Schemas](http://go.microsoft.com/fwlink/?LinkId=169192)를 참조하십시오.|  
|Schema.xml|목록 정의의 스키마 파일입니다.  자세한 내용은 [Building Block: Lists and Document Libraries](http://go.microsoft.com/fwlink/?LinkId=177792) 및 [Schema.xml](http://go.microsoft.com/fwlink/?LinkId=177793)을 참조하십시오.|  
|.webpart|*웹 파트 정의* 파일입니다.  이 파일에는 웹 파트의 속성 설정이 포함됩니다.  자세한 내용은 [Building Block: Web Parts](http://go.microsoft.com/fwlink/?LinkId=177791)를 참조하십시오.|  
|.ascx|ASP.NET UserControl 파일입니다.  이 파일에서는 비주얼 웹 파트의 UI를 정의합니다.|  
|.aspx|ASP.NET 페이지 파일입니다.  이 파일에는 응용 프로그램 페이지를 정의하는 XML 태그가 포함됩니다.|  
|.cs 또는 .vb 파일|이러한 코드 파일에서는 응용 프로그램 페이지, 웹 파트 및 워크플로와 같이 Visual C\# 또는 Visual Basic 코드에서 액세스할 수 있는 프로그래밍 모델이 있는 SharePoint 사용자 지정의 동작을 정의합니다.|  
  
## 프로젝트 템플릿 만들기  
 SharePoint 프로젝트 템플릿을 만드는 경우 항상 필요한 파일과 특정 형식의 프로젝트에서 사용할 수 있는 선택적 파일이 있습니다.  일반적으로 SharePoint 프로젝트에는 하나 이상의 SharePoint 프로젝트 항목이 포함되어 있지만  이것이 필수적인 것은 아닙니다.  예를 들어, 다른 프로젝트에서 만들어진 SharePoint 솔루션을 배포하는 데만 사용할 SharePoint 프로젝트 템플릿을 정의할 수도 있습니다.  
  
 SharePoint 프로젝트 항목 형식을 정의하고 이 형식의 프로젝트 템플릿을 만드는 방법을 보여 주는 연습은 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)를 참조하십시오.  
  
 다음 표에는 SharePoint 프로젝트 템플릿에 포함되어야 하는 파일이 나와 있습니다.  
  
|필수 파일|설명|  
|-----------|--------|  
|.vstemplate 파일|이 파일은 **새 프로젝트** 대화 상자에 템플릿을 표시하고 템플릿에서 프로젝트를 만드는 데 필요한 정보를 Visual Studio에 제공합니다.  자세한 내용은 [NIB: Visual Studio Template Metadata Files](http://msdn.microsoft.com/ko-kr/129d59b5-7f9c-4daf-9832-eaedb3c4c961)을 참조하십시오.|  
|.csproj 또는 .vbproj 파일|프로젝트 파일입니다.  이 파일은 프로젝트의 내용과 구성 설정을 정의합니다.|  
|Package.package|이 파일에서는 프로젝트의 배포 패키지를 정의합니다.  패키지 디자이너를 사용하여 프로젝트의 솔루션 패키지를 사용자 지정하는 경우 Visual Studio에서는 솔루션 패키지에 대한 데이터를 이 파일에 저장합니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 템플릿을 만들 때 최소한의 필요한 내용만 Package.package 파일에 포함하고 프로젝트 템플릿과 연결된 확장에서 <xref:Microsoft.VisualStudio.SharePoint.Packages> 네임스페이스의 API를 사용하여 솔루션 패키지를 구성하는 것이 좋습니다.  이렇게 하는 경우 프로젝트 템플릿이 Package.package 파일 구조에 대한 이후 변경에서 보호됩니다.  최소한의 필요한 내용만 포함된 Package.package 파일을 만드는 방법을 보여 주는 예제를 보려면 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)를 참조하십시오.<br /><br /> Package.package 파일을 직접 수정하려는 경우 %Program Files \(x86\)%\\Microsoft Visual Studio 11.0\\Xml\\Schemas\\PackageModelSchema.xsd에 있는 스키마를 사용하여 내용을 확인할 수 있습니다.|  
|Package.Template.xml|이 파일은 프로젝트에서 생성되는 SharePoint 솔루션 패키지\(.wsp\)에 대한 솔루션 매니페스트 파일\(manifest.xml\)의 기반이 됩니다.  사용자가 변경하면 안 되는 프로젝트 형식의 일부 동작을 지정하려는 경우 이 파일에 내용을 추가할 수 있습니다.  자세한 내용은 [Building Block: Solutions](http://go.microsoft.com/fwlink/?LinkId=169186) 및 [Solution Schema](http://go.microsoft.com/fwlink/?LinkId=177794)를 참조하십시오.<br /><br /> 프로젝트에서 솔루션 패키지를 빌드할 때 Visual Studio에서는 Package.package 및 Package.Template.xml 파일의 내용을 솔루션 매니페스트 파일에 병합합니다.  솔루션 패키지 빌드에 대한 자세한 내용은 [How to: Create a SharePoint Solution Package \(wsp\)](http://msdn.microsoft.com/ko-kr/b24be45c-e91d-49bb-afb0-7b265404214b)를 참조하십시오.|  
  
 다음 표에는 프로젝트 템플릿에 포함될 수 있는 선택적 파일이 나와 있습니다.  
  
|선택적 파일|설명|  
|------------|--------|  
|SharePoint 프로젝트 항목|SharePoint 프로젝트 항목 형식을 정의하는 .spdata 파일을 하나 이상 포함할 수 있습니다.  각 .spdata 파일에는 프로젝트 템플릿이 있는 VSIX 패키지에 포함된 확장 어셈블리에 일치하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현이 있어야 합니다.  자세한 내용은 [항목 템플릿 만들기](#creatingitemtemplates)를 참조하십시오.<br /><br /> 일반적으로 SharePoint 프로젝트에는 하나 이상의 SharePoint 프로젝트 항목이 포함되어 있지만  이것이 필수적인 것은 아닙니다.|  
|*featureName*.feature|이 파일에서는 배포할 몇 가지 프로젝트 항목을 그룹화하는 데 사용되는 SharePoint 기능을 정의합니다.  기능 디자이너를 사용하여 프로젝트의 기능을 사용자 지정하는 경우 Visual Studio에서는 기능에 대한 데이터를 이 파일에 저장합니다.  프로젝트 항목을 여러 기능으로 그룹화하려는 경우에는 여러 .feature 파일을 포함할 수 있습니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 템플릿을 만들 때 최소한의 필요한 내용만 각 .feature 파일에 포함하고 프로젝트 템플릿과 연결된 확장에서 <xref:Microsoft.VisualStudio.SharePoint.Features> 네임스페이스의 API를 사용하여 기능을 구성하는 것이 좋습니다.  이렇게 하는 경우 프로젝트 템플릿이 .feature 파일 구조에 대한 이후 변경에서 보호됩니다.  최소한의 필요한 내용만 포함된 .feature 파일을 만드는 방법을 보여 주는 예제를 보려면 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)를 참조하십시오.<br /><br /> .feature 파일을 직접 수정하려는 경우 %Program Files \(x86\)%\\Microsoft Visual Studio 11.0\\Xml\\Schemas\\FeatureModelSchema.xsd에 있는 스키마를 사용하여 내용을 확인할 수 있습니다.|  
|*featureName*.Template.xml|이 파일은 프로젝트에서 생성되는 각 기능에 대한 기능 매니페스트 파일\(Feature.xml\)의 기반이 됩니다.  사용자가 변경하면 안 되는 프로젝트 형식의 일부 동작을 지정하려는 경우 이 파일에 내용을 추가할 수 있습니다.  자세한 내용은 [Building Block: Features](http://go.microsoft.com/fwlink/?LinkId=169183) 및 [Feature.xml Files](http://go.microsoft.com/fwlink/?LinkId=177795)를 참조하십시오.<br /><br /> 프로젝트에서 솔루션 패키지를 빌드할 때 Visual Studio에서는 각 *featureName*.feature 파일 및 *featureName*.Template.xml 파일 쌍의 내용을 기능 매니페스트 파일에 병합합니다.  솔루션 패키지 빌드에 대한 자세한 내용은 [How to: Create a SharePoint Solution Package \(wsp\)](http://msdn.microsoft.com/ko-kr/b24be45c-e91d-49bb-afb0-7b265404214b)를 참조하십시오.|  
  
## 항목 템플릿 및 프로젝트 템플릿에 대한 마법사 만들기  
 SharePoint 프로젝트 항목 형식을 정의하고 이 형식을 항목 또는 프로젝트 템플릿에 연결한 후에는 마법사를 만들 수도 있습니다.  이 마법사는 개발자가 항목 템플릿을 사용하여 SharePoint 프로젝트 항목을 프로젝트에 추가하거나 프로젝트 템플릿을 사용하여 SharePoint 프로젝트 항목을 포함하는 새 프로젝트를 만드는 경우에 표시됩니다.  이 마법사는 개발자로부터 정보를 수집하고 새 SharePoint 프로젝트 항목을 초기화하는 데 사용될 수 있습니다.  
  
 항목 템플릿과 프로젝트 템플릿에 대한 마법사를 만드는 방법을 보여 주는 연습은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md) 및 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)을 참조하십시오.  
  
## 참고 항목  
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Visual Studio에서 사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)  
  
  