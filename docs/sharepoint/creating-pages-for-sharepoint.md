---
title: "SharePoint에 대한 페이지 만들기"
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
  - "콘텐츠 페이지[Visual Studio에서 SharePoint 개발], 디자인"
  - "마스터 페이지[Visual Studio에서 SharePoint 개발], 디자인"
  - "페이지 레이아웃[Visual Studio에서 SharePoint 개발], 디자인"
  - "Visual Studio에서 SharePoint 개발, 콘텐츠 페이지"
  - "Visual Studio에서 SharePoint 개발, 마스터 페이지"
  - "Visual Studio에서 SharePoint 개발, 페이지 레이아웃"
ms.assetid: 57678ed1-841f-45de-a1d3-5f9e233bf3ce
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# SharePoint에 대한 페이지 만들기
  SharePoint 사이트의 응용 프로그램 페이지, 사이트 페이지, 마스터 페이지 및 페이지 레이아웃을 만들 수 있습니다.  
  
 Visual Studio에서 템플릿을 사용하여 응용 프로그램 페이지를 만들 수 있습니다.  SharePoint Designer를 사용하여 사이트 페이지, 마스터 페이지 및 페이지 레이아웃을 만든 다음  이러한 페이지를 Visual Studio로 가져와서 SharePoint 프로젝트에서 사용할 수 있습니다.  
  
 CSS 스타일시트, ECMAScript 및 테마를 사용하여 페이지의 모양과 동작을 수정할 수도 있습니다.  
  
## SharePoint 페이지 유형  
 다음 표에서는 SharePoint 사이트에 포함되는 네 가지 기본 페이지 유형에 대해 설명합니다.  
  
|페이지 유형|설명|  
|------------|--------|  
|응용 프로그램 페이지|페이지에 사용자 지정 코드를 포함하거나 페이지가 여러 사이트에서 공유되도록 하려는 경우 응용 프로그램 페이지를 만듭니다.  그렇지 않은 경우에는 사이트 페이지를 선택하는 것이 가장 좋습니다.|  
|사이트 페이지|다음 작업 중 하나를 수행하려면 사이트 페이지를 만듭니다.<br /><br /> -   SharePoint 라이브러리에 페이지를 추가합니다.<br />-   페이지에서 동적 웹 파트 및 웹 파트 영역과 같은 기능을 호스팅할 수 있게 합니다.<br />-   사용자가 SharePoint Designer를 사용하여 페이지를 사용자 지정할 수 있게 합니다.<br /><br /> 페이지에 사용자 지정 코드가 포함되도록 하려면 사이트 페이지를 만들지 마십시오.  사이트 페이지에 사용자 지정 코드를 추가할 수는 있지만 사용자가 SharePoint Designer를 사용하여 페이지를 사용자 지정하면 코드의 실행이 중지됩니다.|  
|마스터 페이지|사이트 페이지 및 응용 프로그램 페이지의 일반적 구조를 정의하려면 마스터 페이지를 만듭니다.|  
|페이지 레이아웃|페이지 레이아웃은 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]에서만 사용 가능하며 사이트 페이지 및 응용 프로그램 페이지의 일반적 구조를 세밀히 정의할 수 있게 합니다.|  
  
 페이지의 각 유형의 개요는 [블록 구성 : 페이지 및 사용자 인터페이스](http://go.microsoft.com/fwlink/?LinkID=182095) 및 [페이지 레이아웃 및 마스터 페이지](http://go.microsoft.com/fwlink/?LinkID=182096) 을 참조하십시오.  
  
## 응용 프로그램 페이지 만들기  
 Visual Studio에서 **응용 프로그램 페이지** 항목을 SharePoint 프로젝트에 추가하여 응용 프로그램 페이지를 만들 수 있습니다.  이 페이지에 컨트롤을 추가한 다음 코드를 추가하여 컨트롤 이벤트를 처리할 수 있습니다.  
  
 이 페이지의 코드 파일에서 중단점을 설정하고, 디버거를 시작하고, 로컬 SharePoint 사이트의 페이지를 테스트할 수 있으며 이 과정에서 추가 구성 절차를 수행할 필요는 없습니다.  자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)을 참조하십시오.  
  
## 사이트 페이지, 마스터 페이지 및 페이지 레이아웃 만들기  
 SharePoint Designer를 사용하여 사이트 페이지, 마스터 페이지 및 페이지 레이아웃을 만들 수 있습니다.  그런 다음 이러한 페이지를 Visual Studio로 가져올 수 있습니다.  Visual Studio에서 사용 가능한 배포 또는 소스 제어 기능을 활용하려면 페이지를 가져오십시오.  자세한 내용은 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)을 참조하십시오.  
  
 이러한 페이지는 가져온 이후에는 수정하기 어렵기 때문에 페이지를 가져오기 전에 디자인해야 합니다.  
  
## CSS 스타일시트, ECMAScript 및 테마 만들기  
 Visual Studio에서는 SharePoint 사이트용 CSS 스타일시트, ECMAScript\(JavaScript, JScript\) 또는 테마 파일을 개발할 수 있는 템플릿을 제공하지 않습니다.  이러한 파일은 SharePoint SDK에서 제공하는 지침을 사용하거나 SharePoint Designer 같은 도구를 사용하여 만들 수 있습니다.  
  
 이러한 파일은 솔루션에 직접 추가하거나 Visual Studio로 가져올 수 있습니다.  둘 중 어느 방법을 선택하는지와 상관없이 추가한 각 항목에 대해 적절하게 매핑된 폴더를 만들어야 합니다.  매핑된 폴더를 만드는 방법에 대한 자세한 내용은 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)를 참조하십시오.  
  
 CSS 스타일시트 만들기에 대한 자세한 내용은 [Cascading Style Sheets Class Usage in SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkID=182098) 을 참조하십시오.  SharePoint 솔루션에 필요한 JavaScript 및 JScript 파일을 만드는 방법에 대한 자세한 내용은 [Basic ASPX Page for ECMAScript 설정](http://go.microsoft.com/fwlink/?LinkID=182099) 을 참조하십시오.  테마에 대한 자세한 내용은 [블록 구성: 페이지 및 사용자 인터페이스](http://go.microsoft.com/fwlink/?LinkID=182095) 을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)|응용 프로그램 페이지: SharePoint 마스터 페이지와 병합되는 .aspx 콘텐츠를 추가하는 방법에 대해 설명합니다.|  
|[방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md)|SharePoint 사이트에서 실행되는 ASP.NET 페이지를 만드는 방법을 보여 줍니다.|  
|[연습: SharePoint 응용 프로그램 페이지 만들기](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)|SharePoint 사이트를 위한 ASP.NET 웹 페이지를 디자인하고 디버깅하는 방법을 보여 줍니다.|  
|[Visual Web Developer 작업](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)|프로젝트에서 웹 페이지를 열 때 나타나는 디자이너를 사용하는 방법에 대해 설명합니다.|  
  
  