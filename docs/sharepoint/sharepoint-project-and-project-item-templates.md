---
title: "SharePoint 프로젝트 및 프로젝트 항목 템플릿"
ms.custom: ""
ms.date: "02/22/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.SPE.FirstWizardPage"
  - "VS.SharePointTools.SPE.ListInstance"
  - "VS.SharePointTools.SPE.ListDefinition"
  - "VS.SharePointTools.SPE.ListDefFromContentType"
  - "VS.SharePointTools.SPE.ContentType"
  - "SPE.Wizard"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 프로젝트 및 프로젝트 항목 템플릿"
  - "Visual Studio에서 SharePoint 개발, 템플릿"
ms.assetid: 54a7576f-d3f9-475d-8ed7-b675ad21cb53
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# SharePoint 프로젝트 및 프로젝트 항목 템플릿
  다음 섹션은 사용 가능한 SharePoint 프로젝트 및 프로젝트의 항목 템플릿에 대한 설명과 어떻게 사용하는지에 대해 보여줍니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
##  <a name="project_items_templates_overview"></a> 프로젝트 및 프로젝트 항목 템플릿 개요  
 Visual Studio에서 새 SharePoint 프로젝트를 만들 때, SharePoint 프로젝트는 해당 프로젝트 형식에 필요한 모든 프로젝트 아이템과 함께 솔루션에 추가됩니다.  예를 들어, Silverlight Web Part 프로젝트를 만드는 경우, Visual Studio는 Visual Web Part 프로젝트 항목을 포함하는 솔루션 및 이러한 프로젝트 항목에 필요한 파일들과 함께 Silverlight 응용 프로그램 프로젝트 항목을 만들어 줍니다.  프로젝트 항목 템플릿은 기존 SharePoint 프로젝트에 이벤트 수신자, 사이트 열, 또는 리스트와 같은 프로젝트 항목을 추가하는데 사용됩니다.  
  
 기본 SharePoint에 대한 내용은 [SharePoint Foundation 구성 요소](http://go.microsoft.com/fwlink/?LinkId=179404) 를 참고하시기 바랍니다.  고급 사용자는 사용자 지정 프로젝트 및 프로젝트 항목 템플릿을 만들 수 있습니다.  자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
##  <a name="project_templates"></a> 프로젝트 템플릿  
 다음은 SharePoint 프로젝트 템플릿 목록입니다.  Visual Studio의 **새 프로젝트** 대화 상자에서 SharePoint 프로젝트 템플릿을 보기 위해, **SharePoint** 노드, **Visual C\#** 또는 **Visual Basic** 아래에 있는 노드를 열고 **2010** 을 선택해 줍니다.  
  
### SharePoint 2010 프로젝트  
 이 *SharePoint 2010 프로젝트* 내용은 모든 SharePoint 프로젝트 템플릿에 포함됩니다.  SharePoint 프로젝트에는 다음과 같은 내용을 포함합니다.  
  
-   프로젝트 파일입니다.  
  
-   프로젝트 속성 페이지  
  
-   프로젝트에서의 모든 어셈블리 참조를 표시하는 **References** 폴더  
  
-   SharePoint 서버에 기능을 배포하는데 사용되는 .feature 구성 파일이 포함된 **Features** 폴더  
  
-   SharePoint에 솔루션을 배포하는데 사용되는 Package.package 파일을 포함 하는 **패키지** 폴더.  
  
-   강력한 이름으로 어셈블리에 서명하는데 보안용으로 쓰일 key.snk\(강력한 이름 키\) 파일  
  
### SharePoint 2010 Silverlight 웹 파트  
 이 *SharePoint 2010 Silverlight 웹 파트* 프로젝트를 사용하면 Silverlight 응용 프로그램을 표시하는 SharePoint 용 웹 파트를 만들 수 있습니다.  이 프로젝트를 만드는 경우, 사용자는 새 Silverlight 응용 프로그램을 추가 하거나 기존 참조를 지정할 수 있습니다.  자세한 내용은 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md) 및 [연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)를 참조하십시오.  
  
### SharePoint 2010 비주얼 웹 파트  
 이 *SharePoint 2010 Visual 웹 파트* 프로젝트는 Elements.xml 정의 파일, **웹 파트** 항목, 그리고 **사용자 정의 컨트롤** 항목을 포함합니다.  사용자는 visual 웹 파트의 외관을 Visual Studio 도구 상자로부터 사용자 정의 컨트롤의 화면으로 끌거나 복사를 해서 디자인할 수 있습니다.  자세한 내용은 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) 및 [구성 요소: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438) 를 참고하시기 바랍니다.  
  
### SharePoint 2010 솔루션 패키지 가져오기  
 이 *SharePoint 2010 솔루션 패키지 가져오기* 프로젝트는 Visual Studio로 SharePoint 솔루션 \(.wsp\) 파일로 내보낼 기존 SharePoint 2010 사이트의 전부 또는 일부를 가져올 수 있게 해 줍니다.  한번 Visual Studio로 가져오면, 그 후 항목을 사용자 지정 및 재 배포할 수 있습니다.  자세한 내용은 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)을 참조하십시오.  
  
### 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기  
 이 *다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기* 프로젝트를 사용하면 Visual Studio로 SharePoint Designer 2010에서 만든 재사용 가능한, 선언적 워크플로를 가져올 수 있게 됩니다.  워크플로는 SharePoint 사이트에서 .wsp 파일로 내보낸 것입니다.  한번 Visual Studio로 가져오면, 사용자 지정하고 코드를 추가하여 SharePoint 사이트에 배포할 수 있습니다.  자세한 내용은 [연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)을 참조하십시오.  
  
##  <a name="project_item_templates"></a> 프로젝트 항목 템플릿  
 다음은 SharePoint 프로젝트 항목 템플릿 목록입니다.  SharePoint를 사이트 열, 리스트, 콘텐츠 형식 등의 기능을 기능적으로 지원하기 위해서 프로젝트 항목 템플릿은 SharePoint 솔루션에 파일을 추가 합니다.  예를 들어, 프로젝트에 솔루션에 사이트 열을 추가하면 Elements.xml 정의 파일을 포함하는 사이트 열 프로젝트가 추가됩니다.  visual 웹 파트를 추가하면 Elements.xml 파일, 사용자 컨트롤 항목, 그리고 visual 웹 파트 항목이 포함 된 솔루션에 visual 웹 파트 프로젝트가 추가됩니다.  
  
 SharePoint 프로젝트 항목 템플릿을 **솔루션 탐색기** 에서 보려면, SharePoint 프로젝트에 대한 바로 가기 메뉴를 연 다음 **추가** 에 들어가서 **새 항목** 을 선택해 줍니다.  그리고 **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 클릭합니다.  
  
### 응용 프로그램 페이지\(팜 솔루션에서만 해당\)  
 이 **응용 프로그램 페이지** 항목을 사용하면 SharePoint 사이트의 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 웹 페이지를 디자인할 수 있습니다.  응용 프로그램 페이지는 팜 솔루션 에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md) 와 [응용 프로그램 \_layouts 페이지 유형](http://go.microsoft.com/fwlink/?LinkId=179434) 을 참고하시기 바랍니다.  
  
### 비즈니스 데이터 연결 모델\(팜 솔루션에서만 해당\)  
 이 **비즈니스 데이터 연결 모델** 항목을 사용하면 비즈니스 데이터를 SharePoint에 통합할 수 있습니다.  비즈니스 데이터는 [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)], Siebel, SAP\(Service Advertising Protocol\) 등의 백 엔드 서버 응용 프로그램을 통해 제공될 수 있습니다.  비즈니스 데이터 연결 모델은 팜 솔루션에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md), [방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md), 그리고 [새로운: Business Connectivity Services](http://go.microsoft.com/fwlink/?LinkId=179411) 을 참고하시기 바랍니다.  
  
### 콘텐츠 형식  
 이 *콘텐츠 형식* 프로젝트를 사용하면 문서, 알림 또는 작업과 같은 기존의 \(기본\) 콘텐츠 형식을 기반으로 하여 사용자 지정 콘텐츠 형식을 만들 수 있습니다.  사용자 지정 콘텐츠 형식은 기본 콘텐츠 형식과 동일한 속성 및 필드와 사용자가 정의한 모든 필드를 제공합니다.  예를 들어, SharePoint에서 제공하는 기본 Contact 콘텐츠 형식을 기반으로 하는 사용자 지정 Contact 콘텐츠 형식을 만들 수 있습니다.  사용자는 콘텐츠 형식을 기본 콘텐츠 형식에 이미 포함 된 사이트에 열을 추가하거나 기존 사이트의 열을 변경하여 사용자 지정할 수 있습니다.  
  
> [!NOTE]  
>  SharePoint 제한으로 인해 샌드박스가 적용된 솔루션 콘텐츠 형식에 기반하는 팜 솔루션 콘텐츠 형식은 만들 수 없습니다.  
  
 자세한 내용은 [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 및 [문서 블록: 콘텐츠 형식](http://go.microsoft.com/fwlink/?LinkId=179413) 을 참고하시기 바랍니다.  
  
### 빈 요소  
 이 *빈 요소* 는 프로젝트 또는 프로젝트 항목 템플릿이 부족한 Visual Studio에서 SharePoint 프로젝트 항목들을 정의하는데 주로 사용됩니다.  프로젝트에 빈 요소 항목을 추가하면, EmptyElement\[x\]\(여기서 \[x\]는 고유 번호입니다\) 노드가 만들어집니다.  EmptyElement\[x\]는 Elements.xml 파일을 포함합니다.  이 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 문을 사용하여 Elements.xml에서 원하는 요소를 정의 합니다.  
  
### 이벤트 수신자  
 이 *이벤트 수신기* 는 리스트에 항목이 추가될 때, 웹 항목이 삭제될 때 워크플로가 시작될 때 등 SharePoint 사이트에서 항목들을 위한 이벤트들을 처리 합니다.  이벤트 수신자 프로젝트 템플릿을 사용하여 다음을 처리할 수 있습니다.  
  
-   이벤트 리스트  
  
-   항목 이벤트 리스트  
  
-   전자 메일 이벤트 리스트  
  
-   웹 이벤트  
  
-   워크플로 이벤트 리스트  
  
 이벤트 수신자 프로젝트는 **SharePoint 사용자 지정 마법사** 에서 프로젝트를 만들 때 지정한 모든 이벤트에 대한 이벤트 핸들러들을 포함하는 하나의 클래스 파일과 함께 **Event Receiver** 폴더를 생성합니다.  그리고 event receiver 클래스는 파일, 필드, 항목, 리스트, 첨부 파일, 웹 사이트 및 워크플로와 같은 항목을 추가, 업데이트, 삭제 또는 제거할 때 SharePoint 사이트에서 발생하는 이벤트를 처리할 수 있습니다.  자세한 내용은 [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md) 및 [문서 블록: 이벤트 처리](http://go.microsoft.com/fwlink/?LinkId=179416) 을 참고하시기 바랍니다.  
  
### List  
 리스트는 일정이나 작업 목록과 같은 SharePoint의 재사용 가능한 기본 리스트 정의의 단일 인스턴스 입니다.  솔루션에 리스트를 추가해주면, 리스트 디자이너가 리스트에 사이트 열을 추가 및 사용자 지정 리스트 열을 만들 수 있게 해줍니다.  이것은 콘텐츠 형식에서의 사이트 열을 포함합니다.  또 사용자는 리스트의 *보기* 를, 리스트에 표시될 열을 지정할 수 있습니다.  자세한 내용은 [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 및 [문서 블록: 목록 및 문서 라이브러리](http://go.microsoft.com/fwlink/?LinkId=179421) 을 참고하시기 바랍니다.  
  
### Module  
 \( [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 모듈과는 다른\) 이 *모듈* 은 이미지나 메모같이 사용자가 SharePoint 서버에 배치하고 싶은 모든 파일을 포함합니다.  모듈 프로젝트 항목은 **모듈** 노드를 포함합니다.  모듈 노드는 두가지 프로젝트 항목 템플릿, 모듈의 매니페스트로 사용되는 XML 정의 파일과 placeholder 파일인 sample.txt 파일을 포함합니다.  자세한 내용은 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md) 및 [Modules](http://go.microsoft.com/fwlink/?LinkId=179425) 을 참고하시기 바랍니다.  
  
### 순차 워크플로\(팜 솔루션에서만 해당\)  
 *순차 워크플로*는 마지막 단계가 완료될 때까지 순차적으로 수행되는 일련의 비즈니스 논리 단계입니다.  순차 워크플로는 목록, 문서 등의 SharePoint 항목과 관련된 프로세스를 관리하는 데 사용됩니다.  사이트 수준\(전역\) 워크플로나 목록 수준\(로컬\) 워크플로를 만들 수 있으며, 워크플로를 자동으로 시작할지 또는 수동으로 시작할지를 선택할 수 있습니다.  이 프로젝트 항목은 팜 솔루션 에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md), [Workflows in SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=260555), 그리고 [What's New: Workflow Improvements](http://go.microsoft.com/fwlink/?LinkId=179418) 을 참고하시기 바랍니다.  
  
### Silverlight 웹 파트  
 이 *SharePoint 2010 Silverlight 웹 파트* 프로젝트를 사용하면 Silverlight 응용 프로그램을 표시하는 SharePoint용 웹 파트를 만들 수 있습니다.  솔루션에 이 프로젝트 항목을 추가하면, 사용자는 새 Silverlight 응용 프로그램을 추가할지, 나중에 기존에 있던 것을 참조할지 선택할 수 있게 됩니다.  자세한 내용은 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md) 및 [연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)를 참조하십시오.  
  
### 사이트 열  
 이 *사이트 열* , *필드* 라고 알려진 이 열은 SharePoint 프로젝트에 추가할 수 있는 가장 기본적인 요소 중 하나입니다.  사이트 열은 전화 번호, 텍스트 메모, 또는 연락처 목록에서 연락처의 도시 이름 등의 데이터 형식을 나타냅니다.  자세한 내용은 [SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md) 및  를 참고하시기 바랍니다.  
  
### 사이트 정의\(팜 솔루션에서만 해당\)  
 이 *사이트 정의* 프로젝트 항목은 다음과 같은 파일을 포함 하는 사이트 정의 폴더를 포함합니다.  
  
-   사이트의 기본 웹 페이지로 사용되는 기본 .aspx 페이지  
  
-   사이트의 구성 요소를 정의하는 onet.xml 파일  
  
-   사이트 정의 구성 중 **New SharePoint Site** 페이지의 **Template Selection** 섹션에 나타나는 사이트 정의 구성을 지정하는 webtemp xml 파일  
  
 사이트 정의를 추가해주고 나면, 코드와 파일을 추가하여 기능을 도입할 수 있습니다.  이 프로젝트 항목은 팜 솔루션 에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [SharePoint에 대한 사이트 정의 만들기](../sharepoint/creating-site-definitions-for-sharepoint.md) 및 [사이트 정 및 구성](http://go.microsoft.com/fwlink/?LinkId=260554) 을 참고하시기 바랍니다.  
  
### 상태 머신 워크플로\(팜 솔루션에서만 해당\)  
 *상태 시스템 워크플로*는 비즈니스 논리 상태, 전환 및 작업 집합입니다.  상태 시스템 워크플로의 단계는 순차적으로 수행되지 않고 작업과 상태에 의해 트리거됩니다.  순차 워크플로와 마찬가지로 상태 시스템 워크플로는 목록, 문서 등의 SharePoint 항목에 연결됩니다.  사이트 수준\(전역\) 워크플로나 목록 수준\(로컬\) 워크플로를 만들 수 있습니다.  워크플로를 자동으로 시작할지 또는 수동으로 시작할지를 선택할 수도 있습니다.  이 프로젝트 항목은 팜 솔루션 에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md), [Workflows in SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=260555), 그리고 [What's New: Workflow Improvements](http://go.microsoft.com/fwlink/?LinkId=179418) 을 참고하시기 바랍니다.  
  
### 사용자 정의 컨트롤\(팜 솔루션에서만 해당\)  
 이 *사용자 정의 컨트롤* 은 다른 ASP.NET 컨트롤과 SharePoint 컨트롤을 추가할 수 있는 복합 컨트롤입니다.  사용자 정의 컨트롤은 응용 프로그램 페이지 및 SharePoint에서 실행되는 웹 파트를 추가할 수 있습니다.  이 프로젝트 항목은 팜 솔루션 에서만 사용할 수 있습니다.  팜 솔루션에서만 이 프로젝트 항목을 추가할 수 있습니다.  자세한 내용은 [웹 파트 또는 응용 프로그램 페이지에 대 한 재사용 가능한 컨트롤 만들기](http://go.microsoft.com/fwlink/?LinkId=226841) 를 참고하시기 바랍니다.  
  
### 비주얼 웹 파트  
 이 *visual 웹 파트* 프로젝트 아이템은 Elements.xml 정의 파일, **웹 파트** 항목, 그리고 **사용자 정의 컨트롤** 항목을 포함합니다.  사용자는 visual 웹 파트의 외관을 Visual Studio 도구 상자로부터 사용자 정의 컨트롤의 화면으로 끌거나 복사를 해서 디자인할 수 있습니다.  자세한 내용은 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) 및 [구성 요소: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438) 를 참고하시기 바랍니다.  
  
### 웹 파트  
 서버사이드 컨트롤인 *웹 파트* 는 웹 파트 페이지라고 불리는 특별한 종류의 페이지에서 실행됩니다.  이러한 웹 파트들은 SharePoint 사이트에 표시되는 페이지의 블록들을 구성합니다.  웹 파트 항목은 SharePoint 사이트의 웹 파트를 디자인하는데 사용할 수 있는 파일을 제공합니다.  자세한 내용은 [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md) 및 [구성 요소: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438) 를 참고하시기 바랍니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 제품 및 기술](http://go.microsoft.com/fwlink/?LinkId=178818)  
  
  