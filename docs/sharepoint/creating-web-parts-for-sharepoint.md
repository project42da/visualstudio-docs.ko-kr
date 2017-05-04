---
title: "SharePoint를 위한 웹 파트 만들기 | Microsoft Docs"
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
  - "Microsoft.SharePoint.WebControls.DateTimeControl"
  - "Microsoft.SharePoint.WebControls.CssLink"
  - "Microsoft.SharePoint.WebControls.RssLink"
  - "Microsoft.SharePoint.WebControls.Theme"
  - "Microsoft.SharePoint.WebControls.AspMenu"
  - "Microsoft.SharePoint.WebControls.ListProperty"
  - "Microsoft.SharePoint.WebControls.ProjectProperty"
  - "Microsoft.SharePoint.WebControls.FormsDigest"
  - "Microsoft.SharePoint.WebControls.ScriptLink"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 웹 파트"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 디자인"
ms.assetid: a6349e85-45cf-4766-b856-e25c9f1ffd34
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# SharePoint를 위한 웹 파트 만들기
  웹 파트를 사용하면 사용자가 SharePoint 사이트 페이지의 콘텐츠, 모양 및 동작을 브라우저에서 직접 수정할 수 있습니다.  웹 파트는 웹 파트 페이지 내에서 실행되는 서버 쪽 컨트롤이며 SharePoint 사이트에 표시되는 페이지의 빌딩 블록입니다.  [Building Block: Web Parts](http://go.microsoft.com/fwlink/?LinkID=182097)를 참조하십시오.  
  
 Visual Studio의 템플릿을 사용하여 SharePoint 사이트에서 웹 파트를 만들고 디버깅할 수 있습니다.  
  
## Visual Studio에서 웹 파트 만들기  
 SharePoint 프로젝트에 **웹 파트** 항목을 추가하여 웹 파트를 만듭니다.  **웹 파트**항목은 샌드박스가 적용된 솔루션 또는 팜 솔루션에서 사용할 수 있습니다.  
  
 디자이너를 사용하여 시각적으로 웹 파트를 디자인하려면 **비주얼 웹 파트** 프로젝트를 만들거나 **비주얼 웹 파트** 항목을 SharePoint 프로젝트에 추가합니다.  **비주얼 웹 파트** 항목은 팜 솔루션에서만 사용할 수 있습니다.  
  
### 웹 파트 항목  
 **웹 파트** 항목은 SharePoint 사이트의 웹 파트를 디자인하는 데 사용할 수 있는 파일을 제공합니다.  **웹 파트** 항목을 추가하면 프로젝트에 폴더가 만들어지고 폴더에 여러 가지 파일이 추가됩니다.  다음 표에서는 각 파일에 대해 설명합니다.  
  
|파일|설명|  
|--------|--------|  
|Elements.xml|웹 파트를 배포하기 위해 프로젝트의 기능 정의 파일에서 사용하는 정보가 들어 있습니다.|  
|.webpart 파일|SharePoint에서 웹 파트를 웹 파트 갤러리에 표시하는 데 필요한 정보를 제공합니다.|  
|코드 파일|웹 파트에 컨트롤을 추가하고 웹 파트 내에 사용자 지정 콘텐츠를 생성하는 메서드가 들어 있습니다.|  
  
 자세한 내용은 [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)을 참조하십시오.  
  
### 비주얼 웹 파트 항목  
 비주얼 웹 파트는 Visual Studio의 Visual Web Developer 디자이너를 사용하여 만든 웹 파트입니다.  [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)를 참조하십시오.  
  
 비주얼 웹 파트는 다른 웹 파트와 동일하게 작동합니다.  단추 및 텍스트 상자와 같은 컨트롤을 웹 파트에 추가하려면 XML 파일에 코드를 추가합니다.  그러나 컨트롤을 Visual Studio **도구 상자**에서 웹 파트로 끌거나 복사하여 비주얼 웹 파트에 추가합니다.  그런 다음 디자이너가 XML 파일로 필요한 코드를 생성합니다.  [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)를 참조하십시오.  
  
## SharePoint 컨트롤  
 Visual Studio는 응용 프로그램 페이지와 같은 SharePoint 페이지를 만들기 위해 몇 가지 컨트롤을 제공합니다.  이러한 컨트롤은 **도구 상자**의 **SharePoint 컨트롤**에 있습니다.  이러한 컨트롤의 기능은 SharePoint 사이트 및 목록 페이지에 사용된 ASP.NET 서버 컨트롤을 포함하는 [Microsoft.SharePoint.WebControls](http://go.microsoft.com/fwlink/?LinkId=235315) 네임스페이스에서 파생됩니다.  
  
|컨트롤 이름|설명|  
|------------|--------|  
|[AspMenu](http://go.microsoft.com/fwlink/?LinkId=235307)|ASP 메뉴를 삽입합니다.  버전 제어에 대한 자세한 내용은 [Menu 컨트롤 개요](http://go.microsoft.com/fwlink/?LinkId=235316)를 참조하십시오.|  
|[CssLink](http://go.microsoft.com/fwlink/?LinkId=235308)|**LINK** 요소를 .aspx 페이지에 삽입하고 **CssRegistration**가 정의하는 1개 이상의 외부 스타일 시트에 적용합니다.|  
|[DateTimeControl](http://go.microsoft.com/fwlink/?LinkId=235306)|.aspx 페이지에 DateTime 컨트롤을 삽입합니다.|  
|[FormDigest](http://go.microsoft.com/fwlink/?LinkId=235309)|.aspx 페이지에 보안 유효성 검사를 삽입합니다.|  
|[ListProperty](http://go.microsoft.com/fwlink/?LinkId=235310)|지정된 목록의 속성을 반환합니다.|  
|[ProjectProperty](http://go.microsoft.com/fwlink/?LinkId=235311)|현재 웹 페이지의 전역 속성을 반환합니다.|  
|[RssLink](http://go.microsoft.com/fwlink/?LinkId=235312)|.aspx 페이지에 RSS 피드에 대한 링크를 삽입합니다.|  
|[ScriptLink](http://go.microsoft.com/fwlink/?LinkId=235313)|페이지에 스크립트와 같은 리소스를 레지스터하기 위해 속성과 매서드가 제공되어 페이지 렌더링 시 요청할 수 있습니다.|  
|[테마](http://go.microsoft.com/fwlink/?LinkId=235314)|.aspx 페이지에 테마를 적용합니다.|  
  
## 웹 파트 디버깅  
 다른 Visual Studio 프로젝트를 디버깅할 때와 같은 방법으로 웹 파트가 들어 있는 SharePoint 프로젝트를 디버깅할 수 있습니다.  Visual Studio 디버거를 시작하면 Visual Studio에서 SharePoint 사이트가 열립니다.  
  
 코드 디버깅을 시작하려면 SharePoint에서 웹 파트 페이지에 웹 파트를 추가합니다.  
  
 SharePoint 프로젝트를 디버깅하는 방법에 대한 자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)을 참조하십시오.  
  
## 비주얼 웹 파트 제한  
 Visual Studio부터 샌드박스 SharePoint 솔루션 및 팜 솔루션에 비주얼 웹 파트를 추가할 수 있습니다.  그러나 비주얼 웹 파트는 다음과 같은 제한이 있습니다.  
  
-   비주얼 웹 파트는 대체 가능한 매개 변수를 지원하지 않습니다.  자세한 내용은 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)을 참조하십시오.  
  
-   사용자 컨트롤 또는 비주얼 웹 파트는 비주얼 웹 파트로 끌어 놓거나 복사할 수 없습니다.  이 경우 빌드 오류가 발생합니다.  
  
-   비주얼 웹 파트는 $SPUrl와 같은 SharePoint 서버 토큰을 직접 지원하지 않습니다.  자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md) 항목의 "샌드박스가 적용된 비주얼 웹 파트의 토큰 제한 사항"을 참조하십시오.  
  
-   샌드박스 솔루션의 비주얼 웹 파트에는 "샌드박스를 작동하는 코드 실행 호스트 서비스의 사용자가 너무 많아 요청을 처리하지 못했으므로 샌드박스를 작동하는 코드 실행 요청이 거부되었습니다."라는 오류 메시지가 가끔 표시됩니다. 이 오류에 대한 자세한 내용을 보려면 [SharePoint Developer Team Blog](http://go.microsoft.com/fwlink/?LinkId=225932)의 이 게시물을 참조하십시오.  
  
-   Visual Studio에서 서버 측 JavaScript 디버깅은 지원되지 않지만, 클라이언트 측 JavaScript 디버깅은 지원됩니다.  
  
     인라인 JavaScript를 서버측 태그 파일에 추가할 수 있지만 태그에 추가된 중단점에는 디버깅이 지원되지 않습니다.  JavaScript를 디버깅하려면 태그 파일에서 외부 JavaScript 파일을 참조한 후 JavaScript 파일에 중단점을 설정합니다.  
  
-   인라인 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 코드 디버깅은 태그 파일 대신 생성된 코드 파일에서 수행해야 합니다.  
  
-   비주얼 웹 파트는 `<@ Assembly Src=` 지시문 사용을 지원하지 않습니다.  
  
-   SharePoint 웹 컨트롤 및 일부 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 컨트롤은 SharePoint 샌드박스 환경에서 지원되지 않습니다.  샌드박스 솔루션의 비주얼 웹 파트에 지원되지 않는 컨트롤이 사용되는 경우 "'Microsoft.SharePoint.WebControls 네임스페이스에 'Theme' 형식 또는 네임스페이스가 없습니다."라는 오류가 나타납니다.  
  
 샌드박스가 적용된 솔루션에 대한 자세한 내용은 [샌드박스 솔루션과 팜 솔루션의 차이점](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)를 참조하십시오.  
  
## 이전 스타일의 SharePoint 기반 웹 파트 만들기  
 Visual Studio의 템플릿을 사용하여 SharePoint를 위한 [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] 사용자 지정 웹 파트를 만들 수 있습니다.  새 프로젝트에는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 웹 파트 인프라를 기반으로 만들어진 [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] 웹 파트를 사용하는 것이 좋습니다.  
  
 드물게 이전 스타일의 SharePoint 기반 웹 파트를 사용하여 웹 파트를 만들어야 할 경우가 있습니다.  Visual Studio에서 이러한 형식의 웹 파트를 만들 수는 있지만 이 용도로 디자인된 별도의 템플릿은 제공되지 않습니다.  
  
 어떤 경우에 이전 스타일의 SharePoint를 기반으로 웹 파트를 만드는지 보려면 [Windows SharePoint Services의 웹 파트 인프라](http://go.microsoft.com/fwlink/?LinkId=169290)를 참조하십시오.  이전 스타일의 SharePoint 기반 웹 파트를 사용하여 웹 파트를 만드는 방법에 대한 자세한 내용은 [Walkthrough Creating a Basic SharePoint Web Part](http://go.microsoft.com/fwlink/?LinkId=169288)를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)|SharePoint 페이지를 위한 웹 파트를 만드는 방법을 보여 줍니다.|  
|[방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)|시각적 디자인 화면을 사용하여 SharePoint를 위한 웹 파트를 만드는 방법을 보여 줍니다.|  
|[방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|SharePoint에서 실행되는 응용 프로그램 페이지와 웹 파트에서 사용할 수 있는 재사용 가능한 사용자 지정 컨트롤을 만드는 방법을 보여 줍니다.|  
|[연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)|SharePoint를 위한 웹 파트를 디자인하는 방법에 대해 설명합니다.|  
|[연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)|시각적 디자인 화면으로 컨트롤을 끌어와 SharePoint를 위한 웹 파트를 디자인하는 방법에 대해 설명합니다.|  
|[연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)|Silverlight 응용 프로그램을 호스팅하고 SharePoint 목록의 데이터를 표시하는 SharePoint용 웹 파트를 디자인하는 방법을 설명합니다.|  
|[Visual Web Developer 작업](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)|프로젝트에서 웹 페이지를 열 때 나타나는 디자이너를 사용하는 방법에 대해 설명합니다.|  
  
  