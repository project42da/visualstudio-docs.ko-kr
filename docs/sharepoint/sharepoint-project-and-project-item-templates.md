---
title: "SharePoint 프로젝트 및 프로젝트 항목 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 02/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.SPE.FirstWizardPage
- VS.SharePointTools.SPE.ListInstance
- VS.SharePointTools.SPE.ListDefinition
- VS.SharePointTools.SPE.ListDefFromContentType
- VS.SharePointTools.SPE.ContentType
- SPE.Wizard
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, project and project item templates
- SharePoint development in Visual Studio, templates
ms.assetid: 54a7576f-d3f9-475d-8ed7-b675ad21cb53
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 513b2216a99f37ba3aff1174965470b20921072f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sharepoint-project-and-project-item-templates"></a>SharePoint 프로젝트 및 프로젝트 항목 템플릿
  다음 섹션에서는 사용할 수 있는 SharePoint 프로젝트에 설명 하 고 프로젝트 항목 템플릿 및 사용 방법. 
  
##  <a name="project-and-project-item-templates-overview"></a>프로젝트 및 프로젝트 항목 템플릿 개요  
 Visual Studio에서 새 SharePoint 프로젝트를 만들 때 SharePoint 프로젝트는 해당 프로젝트 형식에 필요한 프로젝트 항목의 모든 함께 솔루션에 추가 됩니다. 예를 들어 Silverlight 웹 파트 프로젝트를 만드는 경우 Visual Studio는 비주얼 웹 파트 프로젝트 항목 및 해당 프로젝트 항목에 필요한 모든 파일 뿐만 아니라 Silverlight 응용 프로그램 프로젝트 항목을 포함 하는 솔루션을 만듭니다. 프로젝트 항목 템플릿은 프로젝트 항목을 한 이벤트 수신기, 사이트 열 또는 목록 추가 하는 등 기존 SharePoint 프로젝트에 추가 하는 데 사용 됩니다.  
  
 SharePoint 기본에 대 한 정보를 참조 하십시오. [SharePoint Foundation 구성 요소](http://go.microsoft.com/fwlink/?LinkId=179404)합니다. 고급 사용자는 사용자 지정 프로젝트 및 프로젝트 항목 템플릿을 만들 수 있습니다. 자세한 내용은 참조 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)합니다.  
  
##  <a name="project-templates"></a>프로젝트 템플릿  
 다음은 SharePoint 프로젝트 템플릿 목록입니다. Visual Studio에서 SharePoint 프로젝트 템플릿을 보려면는 **새 프로젝트** 대화 상자에서 **SharePoint** 노드 아래의 **Visual C#** 또는  **Visual Basic**를 선택한 후 **2010**합니다.  
  
### <a name="sharepoint-2010-project"></a>SharePoint 2010 프로젝트  
 콘텐츠는 *SharePoint 2010 프로젝트* 에 모든 SharePoint 프로젝트 템플릿을 포함 됩니다. SharePoint 2010 프로젝트에 포함 되어 있습니다.  
  
-   프로젝트 파일입니다.  
  
-   프로젝트 속성 페이지입니다.  
  
-   A **참조** 폴더에서 프로젝트의 어셈블리 참조를 모두 나열 합니다.  
  
-   A **기능** SharePoint 서버에 기능을 배포 하는 데 사용 하는.feature 구성 파일이 있는 폴더입니다.  
  
-   A **패키지** 솔루션을 SharePoint에 배포 하는 데 사용 되는 있습니다. 패키지 파일이 있는 폴더입니다.  
  
-   Key.snk (강력한 이름 키) 파일에 대 한 강력한 이름의 어셈블리에 서명 하는 데 사용 되는 보안을 강화 합니다.  
  
### <a name="sharepoint-2010-silverlight-web-part"></a>SharePoint 2010 Silverlight 웹 파트  
 *SharePoint 2010 Silverlight 웹 파트* 프로젝트를 사용 하면 Silverlight 응용 프로그램을 표시 하는 SharePoint에 대 한 웹 파트를 만들 수 있습니다. 이 프로젝트를 만들 때 새 Silverlight 응용 프로그램을 추가 하거나 기존 참조할 것인지를 지정할 수 있습니다. 자세한 내용은 참조 [SharePoint 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md) 및 [연습: SharePoint 용 Silverlight 웹 파트를 해당 표시 OData 만드는](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)합니다.  
  
### <a name="sharepoint-2010-visual-web-part"></a>SharePoint 2010 비주얼 웹 파트  
 A *SharePoint 2010 비주얼 웹 파트* 프로젝트는 Elements.xml 정의 파일에는 **웹 파트** 항목 및 **사용자 정의 컨트롤** 항목입니다. 끌어 놓기, 사용자 정의 컨트롤의 화면으로 Visual Studio 도구 상자에서 컨트롤을 복사 하 여 비주얼 웹 파트의 모양을 디자인할 수 있습니다. 자세한 내용은 참조 [하는 방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) 및 [문서 블록: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438)합니다.  
  
### <a name="import-sharepoint-2010-solution-package"></a>SharePoint 2010 솔루션 패키지 가져오기  
 *SharePoint 2010 솔루션 패키지 가져오기* 프로젝트 Visual Studio에는 SharePoint 솔루션 (.wsp) 파일을 내보낸를 기존 SharePoint 2010 사이트의 일부나 전부를 가져올 수 있도록 합니다. Visual Studio로 가져오면 해당 항목을 사용자 지정할 수 있으며 다시 배포 합니다. 자세한 내용은 참조 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)합니다.  
  
### <a name="import-reusable-sharepoint-2010-workflow"></a>다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기  
 *다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기* 프로젝트를 사용 하면 Visual Studio에 SharePoint Designer 2010에서 만든 다시 사용할 수 있는, 선언적 워크플로 가져옵니다. 워크플로.wsp 파일로 SharePoint 사이트에서 내보내집니다. Visual Studio로 가져온 후 사용자 지정할 수 있습니다, 그리고 코드를 추가, 및 다음 SharePoint 사이트에 배포 합니다. 자세한 내용은 참조 [연습: Visual Studio에 SharePoint Designer의 다시 사용할 수 있는 워크플로 가져오기](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)합니다.  
  
##  <a name="project-item-templates"></a>프로젝트 항목 템플릿  
 다음은 SharePoint 프로젝트 항목 템플릿 목록입니다. 프로젝트 항목 템플릿 사이트 열, 목록, 콘텐츠 형식 등의 SharePoint 기능을 지 원하는 SharePoint 솔루션에 파일을 추가 합니다. 예를 들어 사이트 열을 솔루션에 추가 Elements.xml 정의 파일을 포함 하는 사이트 열 프로젝트를 추가 합니다. 비주얼 웹 파트 추가 Elements.xml 파일 및 사용자 컨트롤 항목에는 비주얼 웹 파트 항목을 포함 하는 솔루션에 비주얼 웹 파트 프로젝트를 추가 합니다.  
  
 SharePoint 프로젝트 항목 템플릿을 보려면 **솔루션 탐색기**을 SharePoint 프로젝트에 대 한 바로 가기 메뉴를 열고 다음 선택 **추가**, **새 항목**합니다. 확장의 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후 **2010**합니다.  
  
### <a name="application-page-farm-solution-only"></a>응용 프로그램 페이지 (팜 솔루션에만 해당)  
 **응용 프로그램 페이지 (팜 솔루션에만 해당)** 항목으로 디자인할 수는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] SharePoint 사이트에 대 한 웹 페이지입니다. 팜 솔루션 에서만에서 응용 프로그램 페이지를 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md) 및 [응용 프로그램 페이지 유형 _layouts](http://go.microsoft.com/fwlink/?LinkId=179434)합니다.  
  
### <a name="business-data-connectivity-model-farm-solution-only"></a>비즈니스 데이터 연결 모델 (팜 솔루션에만 해당)  
 A **비즈니스 데이터 연결 모델 (팜 솔루션에만 해당)** 항목을 사용 하면 SharePoint에 비즈니스 데이터를 통합할 수 있습니다. 비즈니스 데이터와 같은 백 엔드 서버 응용 프로그램에서 가져올 수 있습니다 [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)], Siebel 및 서비스 프로토콜 SAP (알림). 비즈니스 데이터 연결 모델 팜 솔루션 에서만에서 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md), [하는 방법: 리소스 파일을 지정 하는 지역화 된 이름, 속성 및 사용 권한을 사용 하 여](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md), 및 [새로운: 비즈니스 연결 서비스](http://go.microsoft.com/fwlink/?LinkId=179411)합니다.  
  
### <a name="content-type"></a>콘텐츠 형식  
 *콘텐츠 형식* 항목을 사용 하는 문서, 알림 또는 작업 같은 기존 (기본) 콘텐츠 형식에 따라 사용자 지정 콘텐츠 형식을 만들 수 있습니다. 사용자 지정 콘텐츠 형식을 정의 하는 모든 사이트 열 (필드)와 함께 기본 콘텐츠 형식으로 동일한 속성 및 필드를 제공 합니다. 예를 들어 SharePoint에서 제공 되는 기본 연락처 콘텐츠 형식에 기반 하는 사용자 지정 연락처 콘텐츠 형식을 만들 수 있습니다. 기존 사이트 열을 변경 하거나 기본 콘텐츠 형식에 이미 포함 하는 것에 더 많은 사이트 열을 추가 하 여 콘텐츠 형식의 사용자 지정할 수 있습니다.  
  
> [!NOTE]  
>  SharePoint 제한으로 인해 샌드박스 솔루션 콘텐츠 형식에 따라 팜 솔루션 콘텐츠 형식을 만들 수 없습니다.  
  
 자세한 내용은 참조 [연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 및 [문서 블록: 콘텐츠 형식](http://go.microsoft.com/fwlink/?LinkId=179413)합니다.  
  
### <a name="empty-element"></a>빈 요소  
 *빈 요소* 가장 자주 프로젝트 또는 Visual Studio에서 프로젝트 항목 템플릿을 없는 SharePoint 프로젝트 항목을 정의 하는 데 사용 됩니다. 프로젝트에 빈 요소를 추가 하는 경우 노드 이름은 EmptyElement [x](where [x] is a unique number\) is created. [X] EmptyElement Elements.xml 라고 하는 단일 파일이 포함 되어 있습니다. 사용 하 여 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] Elements.xml에서 원하는 요소를 정의 하는 문입니다.  
  
### <a name="event-receiver"></a>이벤트 수신기  
 *이벤트 수신기* 항목 목록에는 항목을 추가 하는 경우, 웹 항목을 삭제 하는 경우 또는 워크플로 시작 될 때 같은 SharePoint 사이트에 대 한 이벤트를 처리 합니다. 이벤트 수신기 프로젝트 항목 템플릿을 사용 하면 있습니다.  
  
-   이벤트 목록  
  
-   목록 항목 이벤트  
  
-   전자 메일의 이벤트 표시  
  
-   웹 이벤트  
  
-   워크플로 이벤트 목록  
  
 이벤트 수신기 프로젝트 항목을 만듭니다는 **이벤트 수신기** 에서 프로젝트를 만들 때 지정 된 모든 이벤트에 대 한 이벤트 처리기를 포함 하는 단일 클래스 파일이 있는 폴더는 **SharePoint 사용자 지정 마법사**합니다. 이벤트 수신기 클래스 파일, 필드, 항목, 목록, 첨부 파일, 웹 파트 및 워크플로 등의 항목을 추가, 업데이트, 삭제 또는 제거 하는 경우 SharePoint 사이트에서 발생 하는 이벤트를 처리할 수 있습니다. 자세한 내용은 참조 [하는 방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md) 및 [문서 블록: 이벤트 처리](http://go.microsoft.com/fwlink/?LinkId=179416)합니다.  
  
### <a name="list"></a>목록  
 목록에는 재사용 가능한 기본 SharePoint 목록 정의 달력 작업 목록 등의 인스턴스입니다. 목록을 솔루션을 추가한 후 목록 디자이너를 사용 하면 사이트 열 목록에 추가 하 고 사용자 지정 목록 열을 만들 수 있습니다. 이 콘텐츠 형식에서 사이트 열을 포함합니다. 지정할 수는 *보기* 목록에 표시 될 열을 결정 하는 목록에 대 한 합니다. 자세한 내용은 참조 [연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 및 [문서 블록: 목록 및 문서 라이브러리](http://go.microsoft.com/fwlink/?LinkId=179421)합니다.  
  
### <a name="module"></a>모듈  
 *모듈* (으로 다름 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 모듈) 이미지 또는 메모와 같은 SharePoint 서버에 배포 하려는 파일을 포함 합니다. 모듈 프로젝트 항목에 포함 된 **모듈** 노드. 두 프로젝트 항목 템플릿을 포함 하는 모듈 노드: 매니페스트 모듈에 대 한 역할을 하는 XML 정의 파일을와 sample.txt 파일, 자리 표시자 파일입니다. 자세한 내용은 참조 [솔루션에 파일 포함을 사용 하 여 모듈](../sharepoint/using-modules-to-include-files-in-the-solution.md) 및 [모듈](http://go.microsoft.com/fwlink/?LinkId=179425)합니다.  
  
### <a name="sequential-workflow-farm-solution-only"></a>순차 워크플로 (팜 솔루션에만 해당)  
 A *순차 워크플로* 일련의 비즈니스 논리 단계를 마지막 단계가 완료 될 때까지 순서 대로 수행 합니다. 순차 워크플로 SharePoint 항목 목록, 문서 등을 포함 하는 프로세스를 관리 하는 데 사용 됩니다. 사이트 수준 (global) 워크플로 또는 목록 수준 (local) 워크플로 만들 수 있습니다 및 자동 또는 수동으로 워크플로 시작 여부를 선택할 수 있습니다. 이 프로젝트 항목은 팜 솔루션 에서만에서 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md), [SharePoint Server 2010에서 워크플로](http://go.microsoft.com/fwlink/?LinkId=260555), 및 [새로운: 워크플로 개선](http://go.microsoft.com/fwlink/?LinkId=179418)합니다.  
  
### <a name="silverlight-web-part"></a>Silverlight 웹 파트  
 *Silverlight 웹 파트* 프로젝트 항목을 사용 하면 Silverlight 응용 프로그램을 표시 하는 SharePoint에 대 한 웹 파트를 만들 수 있습니다. 이 프로젝트 항목을 솔루션에 추가 하면 새 Silverlight 응용 프로그램을 추가 하거나 기존을 나중에 참조할 것인지 선택할 수 있습니다. 자세한 내용은 참조 [SharePoint 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md) 및 [연습: SharePoint 용 Silverlight 웹 파트를 해당 표시 OData 만드는](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)합니다.  
  
### <a name="site-column"></a>사이트 열  
 A *사이트 열*라고도 하는 *필드*, SharePoint 프로젝트에 추가할 수는 가장 기본적인 요소 중 하나입니다. 사이트 열에는 전화 번호, 텍스트 설명 또는 도시 이름과 연락처 목록의 연락처에에서 같은 데이터의 형식을 나타냅니다. 자세한 내용은 참조 [만드는 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md) 및 [열](http://go.microsoft.com/fwlink/?LinkId=226840)합니다.  
  
### <a name="site-definition-farm-solution-only"></a>사이트 정의 (팜 솔루션에만 해당)  
 *사이트 정의* 다음 파일을 포함 하는 사이트 정의 폴더를 포함 하는 프로젝트 항목:  
  
-   사이트에 대 한 기본 웹 페이지도 사용 되는 기본.aspx 페이지.  
  
-   사이트의 구성 요소를 정의 하는 onet.xml 파일입니다.  
  
-   Webtemp xml 파일에 표시 되는 사이트 정의 구성을 지정 하는 **서식 파일 선택** 의 섹션은 **새 SharePoint 사이트** 페이지.  
  
 사이트 정의 추가한 후 코드와 기능을 도입 하는 파일을 추가 합니다. 이 프로젝트 항목은 팜 솔루션 에서만에서 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [SharePoint 용 사이트 정의 만들기](../sharepoint/creating-site-definitions-for-sharepoint.md) 및 [사이트 정 및 구성](http://go.microsoft.com/fwlink/?LinkId=260554)합니다.  
  
### <a name="state-machine-workflow-farm-solution-only"></a>상태 시스템 워크플로 (팜 솔루션에만 해당)  
 A *상태 시스템 워크플로* 는 비즈니스 논리 상태, 전환 및 작업의 집합입니다. 상태 시스템 워크플로의 단계 시퀀스에서 수행 되지 않습니다. 대신, 작업 및 상태에 의해 트리거되는 합니다. 순차 워크플로 처럼 상태 시스템 워크플로 목록, 문서 등의 SharePoint 항목에 연결 됩니다. 다시 한 번, 사이트 수준 (global) 워크플로 또는 목록 수준 (local) 워크플로 만들 수 있습니다. 자동 또는 수동으로 워크플로 시작 여부를 선택할 수 있습니다. 이 프로젝트 항목은 팜 솔루션 에서만에서 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md), [SharePoint Server 2010에서 워크플로](http://go.microsoft.com/fwlink/?LinkId=260555), 및 [새로운: 워크플로 개선](http://go.microsoft.com/fwlink/?LinkId=179418)합니다.  
  
### <a name="user-control-farm-solution-only"></a>사용자 정의 컨트롤 (팜 솔루션에만 해당)  
 A *사용자 정의 컨트롤* 다른 ASP.NET 컨트롤과 SharePoint 컨트롤을 추가할 수 있는 사용자 지정 하 고 재사용 가능한 컨트롤입니다. 응용 프로그램 페이지 및 SharePoint에서 실행 되는 웹 파트에 사용자 정의 컨트롤을 추가할 수 있습니다. 이 프로젝트 항목은 팜 솔루션 에서만에서 사용할 수 있습니다. 팜 솔루션에만이 프로젝트 항목을 추가할 수 있습니다. 자세한 내용은 참조 [웹 파트 또는 응용 프로그램 페이지에 대 한 재사용 가능한 컨트롤 만들기](http://go.microsoft.com/fwlink/?LinkId=226841)합니다.  
  
### <a name="visual-web-part"></a>비주얼 웹 파트  
 A *비주얼 웹 파트* Elements.xml 정의 파일을 포함 하는 프로젝트 항목이 한 **웹 파트** 항목 및 **사용자 정의 컨트롤** 항목입니다. 끌어 놓기, 사용자 정의 컨트롤의 화면으로 Visual Studio 도구 상자에서 컨트롤을 복사 하 여 비주얼 웹 파트의 모양을 디자인할 수 있습니다. 자세한 내용은 참조 [하는 방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) 및 [문서 블록: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438)합니다.  
  
### <a name="web-part"></a>웹 파트  
 A *웹 파트* 특수 한 유형의 웹 파트 페이지를 호출 하는 페이지 내에서 실행 되는 서버 쪽 컨트롤입니다. SharePoint 사이트에 표시 되는 페이지의 구성 요소는 서로입니다. 웹 파트 항목을 SharePoint 사이트에 대 한 웹 파트를 디자인할 수를 사용할 수 있는 파일을 제공 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md) 및 [문서 블록: 웹 파트](http://go.microsoft.com/fwlink/?LinkId=179438)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 제품 및 기술](http://go.microsoft.com/fwlink/?LinkId=178818)  
  
  
