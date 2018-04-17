---
title: SharePoint 용 사이트 정의 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1a9e2a631ae80e878ee5293ec3790f8ac93912e2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-site-definitions-for-sharepoint"></a>SharePoint에 대한 사이트 정의 만들기
  SharePoint 사이트 정의 프로젝트에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 만들 수 있습니다는 *사이트 정의*를 새 SharePoint 사이트에 대 한 기반으로 제공 되 합니다. 이러한 정의 모양 및 동작의 SharePoint 사이트에 있지만 해당 기본 콘텐츠 및 기능 뿐만 아니라 결정합니다. 정의에 미리 구성 된 목록, 콘텐츠 형식, 이벤트 수신기, 이미지 및 기타 항목을 넣을 수 있습니다. SharePoint에는 블로그 등의 사이트 정의가 포함되어 있습니다. 블로그 사이트 정의에 따라 사이트를 만들 때 해당 사이트 목록, 웹 파트 및 블로그 사이트에 필요한 기타 항목을 포함 합니다.  
  
 사이트 정의 대 한 자세한 내용은 참조 [사이트 템플릿 및 정의](http://go.microsoft.com/fwlink/?LinkId=179134)합니다.  
  
## <a name="site-definition-projects"></a>사이트 정의 프로젝트  
 사이트 정의 프로젝트에서는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 제공 해야 하는 SharePoint 사이트는 기본 파일만; 기본 기능을 제공 하지 않습니다. 파일 및 원하는 기능을 제공 하는 콘텐츠를 추가 해야 합니다. 만들고 파일을 추가 하 여 사이트를 수동으로 빌드할 수 있습니다.  
  
## <a name="feature-stapling"></a>스테이플 기능  
 사이트 정의 만들기의 한 가지 이점은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 자동으로 사용 한다는 것 *기능 스테이플*합니다. 기능 스테이플링 사이트 정의 자체에 기능을 포함 하는 대신 사이트 정의에 기능을 연결 합니다. 이 원본 사이트 정의 수정 하지 않고 사이트 정의 사용 하 여 만든 모든 사이트에 기능을 추가할 수 있습니다. 자세한 내용은 참조 [기능 스테이플](http://go.microsoft.com/fwlink/?LinkID=119283)합니다.  
  
## <a name="site-definition-project-components"></a>사이트 정의 프로젝트 연결  
 다음 기본 파일에 추가 된 사이트 정의 솔루션을 만들 때 해당 **SiteDefinition** 노드.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|default.aspx|새 SharePoint 사이트에 대 한 기본 ASPX 홈 페이지입니다.|  
|onet.xml|사이트 정의 서식 파일 및 기본 동작의 구성 요소, 새 사이트의 구성을 지정합니다. 이러한 설정은 콘텐츠 형식 설정 된 기본 목록 보기 문서 서식 파일 등의 특성이 포함 하 고 웹 사이트에 포함 된 파트 수 있습니다. 기본적으로는 `Modules` 섹션에서는 SharePoint 사이트 및 구성 방법에 추가할 파일을 나열 합니다.|  
|webtemp_*SiteDefinitionName*.xml|에 표시 되는 사이트 정의 구성을 지정는 **서식 파일 선택** 의 섹션은 **새 SharePoint 사이트** 페이지.|  
  
 기본적으로 모든 사이트 정의에 저장 됩니다는 *드라이브:*files\common Files\Microsoft Shared\Web Server Extensions\14\TEMPLATE\SiteTemplates 폴더입니다. 각 사이트 정의 고유한 해당 하위 폴더를 있습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[연습: 기본 사이트 정의 프로젝트 만들기](../sharepoint/walkthrough-create-a-basic-site-definition-project.md)|기본 사이트 정의 프로젝트를 만드는 과정을 단계별로 안내 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.|  
|[방법: 사용자 지정 사이트 정 및 구성 만들기](http://go.microsoft.com/fwlink/?LinkId=183309)|기존 사이트 정의 복사한 다음이 사본을 수정 하 여 SharePoint에서 사용자 지정 사이트 정의 만드는 방법을 설명 합니다.|  
|[WebTemp.xml](http://go.microsoft.com/fwlink/?LinkId=183310)|사용할 수 있는 사이트 정의 지정 하는 원본 파일에 설명는 **서식 파일 선택** 의 섹션은 **새 SharePoint 사이트** 페이지.|  
|[SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)|전역 사용에 대 한 SharePoint 솔루션을 준비 하는 방법에 설명 합니다.|  
|[SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)|사용자가 수정할 수 있는 SharePoint 페이지의 일부를 만드는 방법을 설명 합니다.|  
|[웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|응용 프로그램 페이지 및 웹 파트에서 실행 되는 재사용 가능한 컨트롤을 만드는 방법에 대해 설명 합니다.|  
|[Visual Web Developer](http://go.microsoft.com/fwlink/?LinkId=178725)|프로젝트에서 웹 페이지를 열 때 표시 되는 디자이너를 사용 하는 방법을 설명 합니다.|  
|[ASP.NET 웹 페이지 개요](http://go.microsoft.com/fwlink/?LinkId=178726)|구조에 대 한 일반적인 정보를 제공 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 웹 페이지에서 페이지를 처리 하는 방법을 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)], 방법과 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지 XHTML 표준을 준수 하는 태그를 표시 합니다.|  
|[ASP.NET 웹 페이지 구문](http://go.microsoft.com/fwlink/?LinkId=178727)|ASP.NET 페이지를 구성 하는 태그 요소에 설명 합니다.|  
|[ASP.NET 웹 페이지 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=178728)|이벤트 처리기를 만드는 방법에 대 한 정보를 제공 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지 및 클라이언트 스크립트와 함께 작업 하는 방법입니다.|  
|[Windows SharePoint Services에서 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=178729)|제공 되는 관리 되는 개체 모델을 사용 하는 방법을 설명 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)]합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  