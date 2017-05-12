---
title: "SharePoint에 대한 사이트 정의 만들기"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 사이트 정의"
  - "사이트 정의[Visual Studio에서 SharePoint 개발]"
ms.assetid: 83db570d-6b9f-4dab-9e71-db41f17b987a
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# SharePoint에 대한 사이트 정의 만들기
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 SharePoint 사이트 정의 프로젝트를 사용하면 새 SharePoint 사이트의 기반으로 사용되는 *사이트 정의*를 만들 수 있습니다.  이러한 정의는 SharePoint 사이트의 모양과 동작뿐 아니라 기본 콘텐츠와 기능도 결정합니다.  정의에서 미리 구성된 목록, 콘텐츠 형식, 이벤트 수신자, 이미지 및 기타 항목을 추가할 수 있습니다.  SharePoint는 블로그와 같은 일부 사이트 정의를 포함합니다.  블로그 사이트 정의를 기반으로 하여 사이트를 만들면 목록, 웹 파트 및 블로그 사이트에 필요한 기타 항목이 사이트에 포함됩니다.  
  
 사이트 정의 대한 자세한 내용은 [사이트 템플릿 및 정의](http://go.microsoft.com/fwlink/?LinkId=179134) 를 참조하십시오.  
  
## 사이트 정의 프로젝트  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 사이트 정의 프로젝트에서는 SharePoint 사이트에 필요한 기본 파일만 제공하고 기본 기능을 제공하지 않습니다.  원하는 기능을 제공하려면 파일과 콘텐츠를 추가해야 합니다.  필요한 파일을 만들고 추가하여 수동으로 사이트를 빌드할 수 있습니다.  
  
## 기능 스테이플링  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사이트 정의를 만들 경우의 한 가지 이점은 *기능 스테이플링*을 자동으로 사용한다는 것입니다.  기능 스테이플링은 사이트 정의 자체에 기능을 포함하는 대신 사이트 정의에 기능을 연결합니다.  이렇게 하면 원본 사이트 정의를 수정하지 않고 사이트 정의를 사용하여 만든 사이트에 기능을 추가할 수 있습니다.  자세한 내용은 [기능 스테이플링](http://go.microsoft.com/fwlink/?LinkID=119283) 을 참조하십시오.  
  
## 사이트 정의 프로젝트 연결  
 사이트 정의 솔루션을 만들면 다음과 같은 기본 파일이 **SiteDefinition** 노드에 추가됩니다.  
  
|파일 이름|설명|  
|-----------|--------|  
|default.aspx|새 SharePoint 사이트의 기본 ASPX 홈 페이지입니다.|  
|onet.xml|새 사이트, 사이트 정의 템플릿의 구성 요소 및 기본 동작의 구성을 지정합니다.  이러한 설정에는 사용할 수 있는 콘텐츠 형식, 기본 목록 뷰, 문서 템플릿 파일, 사이트에 포함된 웹 파트 등의 특성이 포함될 수 있습니다.  기본적으로 `Modules` 섹션에는 SharePoint 사이트에 추가될 파일과 이러한 파일의 구성 방법이 표시됩니다.|  
|webtemp\_*SiteDefinitionName*.xml|**새 SharePoint 사이트** 페이지의 **템플릿 선택** 섹션에 나타나는 사이트 정의 구성을 지정합니다.|  
  
 기본적으로 모든 사이트 정의는 *drive:*\\Program Files\\Common Files\\Microsoft Shared\\Web Server Extensions\\14\\TEMPLATE\\SiteTemplates 폴더에 저장됩니다.  각 사이트 정의에는 해당 하위 폴더가 있습니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[연습: 기본 사이트 정의 프로젝트 만들기](../sharepoint/walkthrough-create-a-basic-site-definition-project.md)|[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 기본 사이트 정의 프로젝트를 만드는 과정을 단계별로 안내합니다.|  
|[방법: 사용자 지정 사이트 정의 및 구성 만들기](http://go.microsoft.com/fwlink/?LinkId=183309)|기존 사이트 정의를 복사한 다음 복사본을 수정하여 SharePoint에서 사용자 지정 사이트 정의를 만드는 방법에 대해 설명합니다.|  
|[WebTemp.xml](http://go.microsoft.com/fwlink/?LinkId=183310)|**새 SharePoint 사이트** 페이지의 **템플릿 선택** 섹션에서 사용할 수 있는 사이트 정의를 지정하는 원본 파일에 대해 설명합니다.|  
|[SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)|전 세계에서 사용하기 위해 SharePoint 솔루션을 준비하는 방법에 대해 설명합니다.|  
|[SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)|사용자가 수정할 수 있는 SharePoint 페이지 부분을 만드는 방법에 대해 설명합니다.|  
|[웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|응용 프로그램 페이지와 웹 파트에서 실행되는 다시 사용 가능한 사용자 정의 컨트롤을 만드는 방법에 대해 설명합니다.|  
|[Visual Web Developer](http://go.microsoft.com/fwlink/?LinkId=178725)|프로젝트에서 웹 페이지를 열 때 나타나는 디자이너를 사용하는 방법에 대해 설명합니다.|  
|[ASP.NET 웹 페이지 개요](http://go.microsoft.com/fwlink/?LinkId=178726)|[!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 웹 페이지의 구조, [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)]에서 페이지를 처리하는 방법 및 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지에서 XHTML 표준에 맞는 태그를 표시하는 방법에 대한 일반적인 내용을 제공합니다.|  
|[ASP.NET 웹 페이지 구문](http://go.microsoft.com/fwlink/?LinkId=178727)|ASP.NET 페이지를 구성하는 태그 요소에 대해 설명합니다.|  
|[ASP.NET 웹 페이지 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=178728)|[!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지에서 이벤트 처리기를 만드는 방법과 클라이언트 스크립트로 작업하는 방법에 대해 설명합니다.|  
|[Windows SharePoint Services 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=178729)|[!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)]에 제공된 관리되는 개체 모델을 사용하는 방법에 대해 설명합니다.|  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  