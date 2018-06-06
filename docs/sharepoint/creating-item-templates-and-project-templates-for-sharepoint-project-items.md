---
title: 항목 템플릿 및 프로젝트 템플릿 만들기 SharePoint 프로젝트 항목에 대 한 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- .spdata files
- projects [SharePoint development in Visual Studio], creating custom templates
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, creating custom project and item templates
- project items [SharePoint development in Visual Studio], creating custom templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b789072b7a9cc84965e3d78a412631120783b40b
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765208"
---
# <a name="creating-item-templates-and-project-templates-for-sharepoint-project-items"></a>SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의한 경우 다른 개발자가 Visual Studio에서 프로젝트 항목을 사용할 수 있도록 항목 템플릿을 또는 프로젝트 템플릿에 연결할 수 있습니다. 템플릿에 대해 마법사를 만들 수 있습니다.  
  
 예를 들어 Visual Studio 프로젝트 템플릿 또는 SharePoint 사이트에 필드를 추가 하기 위한 항목 템플릿을 포함 되지 않습니다. SharePoint 프로젝트 항목 형식 필드를 나타내는 정의 하 고 다른 개발자가 SharePoint 프로젝트에 필드 항목을 추가 하는 데 사용할 수 있는 항목 템플릿을 작성 수 있습니다. 또는 개발자가 필드 항목이 포함 된 새로운 SharePoint 프로젝트를 만들 수 있도록 프로젝트 템플릿을 생성할 수 있습니다. 두 경우 모두 개발자가 사용자 템플릿을 사용 하는 경우 표시 되는 마법사를 제공할 수 있습니다. 이 마법사는 새 항목 또는 프로젝트를 구성 하는 개발자 로부터 정보를 수집할 수 있습니다.  
  
 항목 템플릿 및 프로젝트 템플릿은 *.zip* Visual Studio에서 프로젝트 항목 또는 프로젝트를 만드는 데 사용 되는 파일을 포함 하는 파일입니다. 항목 템플릿 및 프로젝트 템플릿의 기본 사항에 대 한 자세한 내용은 참조 [프로젝트 만들기 및 항목 템플릿](/visualstudio/ide/creating-project-and-item-templates)합니다.  
  
## <a name="create-item-templates"></a>항목 템플릿 만들기
 SharePoint 프로젝트 항목에 대 한 항목 템플릿을 만들 때 몇 가지 사항은 항상 파일 및 특정 종류의 프로젝트 항목에서 사용 될 수 있는 선택적 파일입니다. SharePoint 프로젝트 항목 형식 정의 및 항목 템플릿을 만드는 방법을 보여 주는 연습을 참조 하십시오. [연습: 항목 템플릿, 1 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)합니다.  
  
 다음 표에 SharePoint 프로젝트 항목에 대 한 항목 템플릿을 만드는 데 필요한 파일이 있습니다.  
  
|필수 파일|설명|  
|-------------------|-----------------|  
|*.spdata* 파일|이것이 내용과 프로젝트 항목의 기본 동작을 지정 하는 XML 파일입니다. 이 파일 항목 템플릿에 포함 되어야 합니다. 내용에 대 한 자세한 내용은 *.spdata* 파일, 참조 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)합니다.|  
|A *.vstemplate* 파일입니다.|이 파일은 Visual Studio에서 템플릿을 표시 하는 데 필요한 정보로 제공는 **새 항목 추가** 대화 상자 템플릿에서 프로젝트 항목을 만들 수 있습니다. 이 파일 항목 템플릿에 포함 되어야 합니다. 자세한 내용은 참조 [Visual Studio 템플릿 메타 데이터 파일](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961)합니다.|  
|구현 하는 Visual Studio 확장명 어셈블리는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스입니다.|이 어셈블리는 프로젝트 항목의 런타임 동작을 정의합니다. 이 어셈블리 항목 템플릿 사용 하 여 VSIX 패키지에 포함 되어야 합니다. 자세한 내용은 참조 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md) 및 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.|  
  
 다음 표에서 가장 일반적인 항목 템플릿에 포함 될 수 있는 선택적 파일이 보여 줍니다. 프로젝트 항목의 일부 형식은 여기에 나열 되지 다른 파일에 필요할 수 있습니다.  
  
|선택적 파일|설명|  
|-------------------|-----------------|  
|*Elements.xml*|A *기능 요소* 파일입니다. 이 파일의 UI 및 프로젝트 항목에 의해 만들어진 사용자 지정 동작을 정의 합니다. 이 파일의 내용을 정의 하는 다른 스키마를 포함 하는 각 유형의 같은 인스턴스를 표시, 콘텐츠 형식 또는 사용자 지정 동작을 사용자 지정 합니다. 자세한 내용은 참조 [문서 블록: 기능](http://go.microsoft.com/fwlink/?LinkId=169183) 및 [기능 스키마](http://go.microsoft.com/fwlink/?LinkId=169192)합니다.|  
|*Schema.xml*|목록 정의 대 한 스키마 파일입니다. 자세한 내용은 참조 [문서 블록: 목록 및 문서 라이브러리](http://go.microsoft.com/fwlink/?LinkId=177792) 및 [Schema.xml](http://go.microsoft.com/fwlink/?LinkId=177793)합니다.|  
|*.webpart*|A *웹 파트 정의* 파일입니다. 이 파일에는 웹 파트에 대 한 속성 설정을 포함합니다. 자세한 내용은 참조 [문서 블록: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=177791)합니다.|  
|*.ascx*|ASP.NET UserControl 파일입니다. 이 파일에는 비주얼 웹 파트의 UI를 정의합니다.|  
|*.aspx*|ASP.NET 페이지 파일입니다. 이 파일에는 응용 프로그램 페이지를 정의 하는 XML 태그가 포함 됩니다.|  
|*.cs* 또는 *.vb* 파일|이러한 코드 파일의 Visual C# 또는 Visual Basic 코드, 응용 프로그램 페이지, 웹 파트 워크플로 등에서 액세스할 수 있는 프로그래밍 모델을 가져야 하는 SharePoint 사용자 지정 동작을 정의 합니다.|  
## <a name="create-project-templates"></a>프로젝트 템플릿 만들기
 SharePoint 프로젝트 템플릿을 만들 때에 다음과 같은 일부 파일은 항상 특정 종류의 프로젝트에서 사용할 수 있는 필수 및 선택적 파일입니다. 일반적으로 SharePoint 프로젝트는 SharePoint 프로젝트 항목을 하나 이상 포함 됩니다. 그러나 필요 하지 않습니다. 예를 들어 다른 프로젝트에서 만든 SharePoint 솔루션을 배포 하는 데에 사용 되는 SharePoint 프로젝트 템플릿을 정의할 수 있습니다.  
  
 SharePoint 프로젝트 항목 형식 정의 대 한 프로젝트 템플릿을 작성 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)합니다.  
  
 다음 표에서 SharePoint 프로젝트 템플릿에 포함 되어야 하는 파일을 나열 합니다.  
  
|필수 파일|설명|  
|-------------------|-----------------|  
|A *.vstemplate* 파일|이 파일은 Visual Studio에서 템플릿을 표시 하는 데 필요한 정보로 제공는 **새 프로젝트** 대화 상자 템플릿에서 프로젝트를 만들 수 있습니다. 자세한 내용은 참조 [Visual Studio 템플릿 메타 데이터 파일](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961)합니다.|  
|A *.csproj* 또는 *.vbproj* 파일|프로젝트 파일입니다. 내용과 프로젝트의 구성 설정을 정의합니다.|  
|*있습니다. 패키지*|이 파일은 프로젝트에 대 한 배포 패키지를 정의합니다. 패키지 디자이너를 사용 하 여 프로젝트에 대 한 솔루션 패키지를 사용자 지정 Visual Studio 솔루션 패키지에 대 한 데이터를이 파일에 저장 합니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 템플릿을 만들 때의 최소 필요한 내용만 포함 하는 것이 좋습니다는 *있습니다. 패키지* 파일과의 Api를 사용 하 여 솔루션 패키지를 구성 하는 <xref:Microsoft.VisualStudio.SharePoint.Packages> 프로젝트 템플릿과 사용 하 여 연결 된 확장의 네임 스페이스입니다. 이 작업을 수행 하는 경우 프로젝트 템플릿을의 구조에 나중에 변경 내용에서 보호 되는 *있습니다. 패키지* 파일입니다. 만드는 방법을 보여 주는 예제는 *있습니다. 패키지* 만 최소한으로 파일 내용을 참조 하십시오. [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)합니다.<br /><br /> 수정 하려는 경우는 *있습니다. 패키지* 에서 스키마를 사용 하 여 콘텐츠를 확인할 수 있습니다, 파일을 직접 *% Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas\PackageModelSchema.xsd* .|  
|*Package.Template.xml*|이 파일은 솔루션의 매니페스트 파일에 대 한 기본 제공 (*manifest.xml*) SharePoint 솔루션 패키지에 대 한 (*.wsp*) 프로젝트에서 생성 된 합니다. 프로젝트 형식의 사용자가 변경할 수는 사용 되지 않는 몇 가지 동작을 지정 하려는 경우이 파일에 콘텐츠를 추가할 수 있습니다. 자세한 내용은 참조 [문서 블록: 솔루션](http://go.microsoft.com/fwlink/?LinkId=169186) 및 [솔루션 스키마](http://go.microsoft.com/fwlink/?LinkId=177794)합니다.<br /><br /> 프로젝트에서 솔루션 패키지를 빌드할 때 Visual Studio의 콘텐츠를 병합 하는 *있습니다. 패키지* 및 *Package.Template.xml* 매니페스트 파일을 솔루션에는 파일입니다. 솔루션 패키지를 작성 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: SharePoint 솔루션 패키지 (wsp) 만들기](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b)합니다.|  
  
 다음 표에서 프로젝트 템플릿에 포함 될 수 있는 선택적 파일을 나열 합니다.  
  
|선택적 파일|설명|  
|-------------------|-----------------|  
|SharePoint 프로젝트 항목|SharePoint 프로젝트 항목 형식 정의 하는 하나 이상의.spdata 파일을 포함할 수 있습니다. 각 *.spdata* 짝이 되는 파일 있어야 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 프로젝트 템플릿 사용 하 여 VSIX 패키지에 포함 된 확장 프로그램 어셈블리에 구현 합니다. 자세한 내용은 참조 [항목 템플릿 만들기](#creatingitemtemplates)합니다.<br /><br /> 일반적으로 SharePoint 프로젝트는 SharePoint 프로젝트 항목을 하나 이상 포함 됩니다. 그러나 필요 하지 않습니다.|  
|*{featureName}.feature*|이 파일은 배포에 대 한 여러 프로젝트 항목을 그룹화 하는 데 사용 되는 SharePoint 기능을 정의 합니다. 기능 디자이너를 사용 하 여 프로젝트의 기능을 사용자 지정 Visual Studio 기능에 대 한 데이터를이 파일에 저장 합니다. 다양 한 기능에 프로젝트 항목을 그룹화 하려는 경우에 여러를 포함할 수 있습니다 *.feature* 파일입니다.<br /><br /> 사용자 지정 SharePoint 프로젝트 템플릿을 만들 때 각에 최소 필수 콘텐츠를 포함 하는 것이 좋습니다 *.feature* 파일과의 Api를 사용 하 여 기능을 구성할는 <xref:Microsoft.VisualStudio.SharePoint.Features> 네임 스페이스에는 확장 프로그램 프로젝트 템플릿에 연결 되어 있으므로입니다. 이 작업을 수행 하는 경우 프로젝트 템플릿을의 구조에 나중에 변경 내용에서 보호 되는 *.feature* 파일입니다. 만드는 방법을 보여 주는 예제는 *.feature* 만 최소한으로 파일 내용을 참조 하십시오. [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)합니다.<br /><br /> 수정 하려는 경우는 *.feature* 에서 스키마를 사용 하 여 콘텐츠를 확인할 수 있습니다, 파일을 직접 *% Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas\FeatureModelSchema.xsd*합니다.|  
|*{featureName)입니다. Template.xml 파일*|이 파일은 기능 매니페스트 파일에 대 한 기본 제공 (*Feature.xml*) 프로젝트에서 생성 되는 각 기능에 대 한 합니다. 프로젝트 형식의 사용자가 변경할 수는 사용 되지 않는 몇 가지 동작을 지정 하려는 경우이 파일에 콘텐츠를 추가할 수 있습니다. 자세한 내용은 참조 [문서 블록: 기능](http://go.microsoft.com/fwlink/?LinkId=169183) 및 [Feature.xml](http://go.microsoft.com/fwlink/?LinkId=177795) 파일입니다.<br /><br /> 프로젝트에서 솔루션 패키지를 빌드할 때 Visual Studio의 각 쌍의 콘텐츠를 병합 하는 *{featureName}.feature* 파일 및 *{featureName}. Template.xml 파일* 는 기능으로 파일 매니페스트 파일. 솔루션 패키지를 작성 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: SharePoint 솔루션 패키지 (wsp) 만들기](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b)합니다.|  
  
## <a name="create-wizards-for-item-templates-and-project-templates"></a>항목 템플릿 및 프로젝트 템플릿에 대 한 마법사 만들기
 SharePoint 프로젝트 항목 형식을 정의 하 고 항목이 나 프로젝트 템플릿을 사용 하 여 연결 하는 마법사도 만들 수 있습니다. 개발자는 프로젝트에 SharePoint 프로젝트 항목을 추가 하려면 항목 템플릿을 사용 하거나 개발자가 SharePoint 프로젝트 항목을 포함 하는 새 프로젝트를 만드는 프로젝트 템플릿을 사용 마법사에 표시 됩니다. 개발자 로부터 정보를 수집 하 고 새 SharePoint 프로젝트 항목을 초기화 하는 마법사를 사용할 수 있습니다.  
  
 항목 템플릿 및 프로젝트 템플릿에 대 한 마법사를 만드는 방법을 보여 주는 연습을 참조 하십시오. [연습: 항목 템플릿, 2 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md) 및 [연습: 사이트 만들기 프로젝트 템플릿 사용 하 여 열 프로젝트 항목 2 부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)합니다.  
  
## <a name="see-also"></a>참고자료
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [연습: 항목 템플릿, 1 부와 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [연습: 항목 템플릿을 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기, 2 부](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](/visualstudio/ide/creating-project-and-item-templates)  
  
 