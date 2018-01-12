---
title: "SharePoint를 위한 웹 파트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.SharePoint.WebControls.DateTimeControl
- Microsoft.SharePoint.WebControls.CssLink
- Microsoft.SharePoint.WebControls.RssLink
- Microsoft.SharePoint.WebControls.Theme
- Microsoft.SharePoint.WebControls.AspMenu
- Microsoft.SharePoint.WebControls.ListProperty
- Microsoft.SharePoint.WebControls.ProjectProperty
- Microsoft.SharePoint.WebControls.FormsDigest
- Microsoft.SharePoint.WebControls.ScriptLink
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, Web Parts
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d0c5acfac06702894f67a8bfc1547462a0069e15
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="creating-web-parts-for-sharepoint"></a>SharePoint를 위한 웹 파트 만들기
  웹 파트를 사용 하 여 브라우저를 사용 하 여 콘텐츠, 모양 및 SharePoint 사이트의 페이지의 동작을 수정할 수 있습니다. 웹 파트는 웹 파트 페이지 내에서 실행 되는 서버 쪽 컨트롤: SharePoint 사이트에 표시 되는 페이지의 구성 요소를 수 있습니다. 참조 [문서 블록: 웹 파트](http://go.microsoft.com/fwlink/?LinkID=182097)합니다.  
  
 만들 하 고 Visual Studio에서 템플릿을 사용 하 여 SharePoint 사이트에서 웹 파트를 디버그할 수 있습니다.  
  
## <a name="creating-a-web-part-in-visual-studio"></a>Visual Studio에서 웹 파트 만들기  
 추가 하 여 웹 파트 만들기는 **웹 파트** 을 SharePoint 프로젝트 항목입니다. 사용할 수는 **웹 파트** 샌드박스 솔루션 또는 팜 솔루션 항목입니다.  
  
 만들기, 디자이너를 사용 하 여 웹 파트를 시각적으로 디자인 하려는 경우는 **비주얼 웹 파트** 프로젝트 또는 추가 **비주얼 웹 파트** 을 SharePoint 프로젝트 항목입니다. 사용할 수는 **비주얼 웹 파트** 항목은 팜 솔루션만 합니다.  
  
### <a name="web-part-item"></a>웹 파트 항목입니다.  
 A **웹 파트** 항목은 SharePoint 사이트에 대 한 웹 파트를 디자인 하는 데 사용할 수 있는 파일을 제공 합니다. 추가 하는 경우는 **웹 파트** 항목, Visual Studio 프로젝트에 폴더를 만듭니다를 다음 폴더에 여러 개의 파일을 추가 합니다. 다음 표에서 각 파일에 설명 합니다.  
  
|파일|설명|  
|----------|-----------------|  
|Elements.xml|웹 파트를 배포 하 여 프로젝트의 기능 정의 파일을 사용 하는 정보가 포함 됩니다.|  
|.webpart 파일|SharePoint 웹 파트 갤러리에서 웹 파트를 표시 하는 정보를 제공 합니다.|  
|코드 파일|웹 파트에 컨트롤을 추가 하 고 웹 파트 내 사용자 지정 콘텐츠를 생성 하는 메서드가 포함 됩니다.|  
  
 자세한 내용은 참조 [하는 방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)합니다.  
  
### <a name="visual-web-part-item"></a>비주얼 웹 파트 항목입니다.  
 비주얼 웹 파트는 Visual Studio에서 Visual Web Developer 디자이너를 사용 하 여 만든 웹 파트. 비주얼 웹 파트에는 다른 웹 파트와 동일 하 게 작동 합니다. 단추 및 텍스트 상자 같은 컨트롤에는 웹 파트를 추가 하려면 XML 파일에 코드를 추가 합니다. 끌어 놓기, Visual Studio에서 웹 파트에 복사 하 여 비주얼 웹 파트에 컨트롤을 추가 하는 반면 **도구 상자**합니다. 디자이너는 다음 XML 파일에서 필요한 코드를 생성합니다. 참조 [하는 방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)합니다.  
  
## <a name="sharepoint-controls"></a>SharePoint 컨트롤  
 Visual Studio 응용 프로그램 페이지와 같은 SharePoint 페이지를 만들기 위한 몇 가지 컨트롤을 제공 합니다. 이러한 컨트롤에 표시 된 **도구 상자** 아래 **SharePoint 컨트롤**합니다. 이러한 컨트롤에 대 한 기능에서 파생 되는 [Microsoft.SharePoint.WebControls](http://go.microsoft.com/fwlink/?LinkId=235315) SharePoint 사이트 및 목록 페이지에서 사용 되는 ASP.NET 서버 컨트롤을 포함 하는 네임 스페이스입니다.  
  
|컨트롤 이름|설명|  
|------------------|-----------------|  
|[AspMenu](http://go.microsoft.com/fwlink/?LinkId=235307)|ASP 메뉴를 삽입합니다. 자세한 내용은 참조 [메뉴 컨트롤 개요](http://go.microsoft.com/fwlink/?LinkId=235316)합니다.|  
|[CssLink](http://go.microsoft.com/fwlink/?LinkId=235308)|삽입 한 **링크** 요소.aspx 페이지에 의해 정의 된 하나 이상의 외부 스타일 시트를 적용 하 고 **CssRegistration**합니다.|  
|[DateTimeControl](http://go.microsoft.com/fwlink/?LinkId=235306)|.Aspx 페이지에는 DateTime 컨트롤을 삽입합니다.|  
|[FormDigest](http://go.microsoft.com/fwlink/?LinkId=235309)|.Aspx 페이지에 보안 유효성 검사를 삽입합니다.|  
|[ListProperty](http://go.microsoft.com/fwlink/?LinkId=235310)|지정 된 목록의 속성을 반환합니다.|  
|[ProjectProperty](http://go.microsoft.com/fwlink/?LinkId=235311)|현재 웹 사이트의 전역 속성을 반환 합니다.|  
|[RssLink](http://go.microsoft.com/fwlink/?LinkId=235312)|RSS 피드.aspx 페이지에 대 한 링크를 삽입 합니다.|  
|[ScriptLink](http://go.microsoft.com/fwlink/?LinkId=235313)|페이지를 렌더링할 때 요청할 수 있도록 페이지에서 스크립트와 같은 리소스를 등록 하기 위한 메서드와 속성을 제공 합니다.|  
|[테마](http://go.microsoft.com/fwlink/?LinkId=235314)|.Aspx 페이지에는 테마를 적용합니다.|  
  
## <a name="debugging-a-web-part"></a>웹 파트를 디버깅합니다.  
 다른 Visual Studio 프로젝트를 디버그할 때와 마찬가지로 웹 파트를 포함 하는 SharePoint 프로젝트를 디버깅할 수 있습니다. Visual Studio 디버거를 시작할 때 Visual Studio는 SharePoint 사이트를 엽니다.  
  
 프로그램 코드를 디버깅을 시작 하려면 sharepoint에서 웹 파트 페이지에 웹 파트를 추가 합니다.  
  
 SharePoint 프로젝트를 디버깅 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)합니다.  
  
## <a name="visual-web-part-limitations"></a>비주얼 웹 파트 제한  
 부터는 Visual Studio에서 SharePoint 솔루션 샌드박스 솔루션과 팜 솔루션에 비주얼 웹 파트를 추가할 수 있습니다. 그러나 비주얼 웹 파트는 다음과 같은 제한 사항이 있습니다.  
  
-   비주얼 웹 파트는 대체 가능 매개 변수를 지원 하지 않습니다. 자세한 내용은 참조 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)합니다.  
  
-   사용자 정의 컨트롤 또는 비주얼 웹 파트 놓 및 삭제 하거나 수 없습니다 비주얼 웹 파트에 복사 합니다. 이 동작은 빌드 오류에 설명 합니다.  
  
-   비주얼 웹 파트 $SPUrl 같은 SharePoint 서버 토큰 직접 지원 하지 않습니다. 자세한 내용은 항목의 "토큰 제한 사항에 샌드박스 비주얼 웹 파트" 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)합니다.  
  
-   경우에 따라 오류가 샌드박스 솔루션의 비주얼 웹 파트, "샌드박스 코드 실행 요청이 거부 되었습니다 호스트 서비스 사용량이 너무 많아 요청을 처리할 수 없음을." 이 오류에 대 한 자세한 내용은이 게시물을 참조 하십시오.는 [SharePoint 개발자 팀 블로그](http://go.microsoft.com/fwlink/?LinkId=225932)합니다.  
  
-   Visual Studio에서 지원 되지 않거나 서버 쪽 JavaScript 디버깅 하지만 클라이언트 쪽 JavaScript 디버깅은 지원 됩니다.  
  
     인라인 JavaScript 서버 쪽 태그 파일을 추가할 수 있지만 디버깅의 태그에 추가 하는 중단점 지원 되지 않습니다. JavaScript를 디버깅 하려면 태그 파일에서 외부 JavaScript 파일을 참조 하 고 JavaScript 파일에 중단점을 설정 합니다.  
  
-   인라인의 디버깅 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 태그 파일 대신 생성 된 코드 파일에서 코드를 수행 해야 합니다.  
  
-   비주얼 웹 파트의 사용을 지원 하지 않습니다는 `<@ Assembly Src=` 지시문입니다.  
  
-   SharePoint 웹 컨트롤 및 일부 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 컨트롤 SharePoint sandboxed 환경에서 지원 되지 않습니다. 샌드박스 솔루션으로는 오류에 비주얼 웹 파트에서 지원 되지 않는 컨트롤을 사용 하면 "형식 또는 네임 스페이스 이름 'Theme' 'Microsoft.SharePoint.WebControls' 네임 스페이스에 존재 하지 않는" 나타납니다.  
  
 샌드박스 솔루션에 대 한 자세한 내용은 참조 [차이점 샌드박스 솔루션과 팜 솔루션 간](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)합니다.  
  
## <a name="creating-older-style-sharepoint-based-web-parts"></a>이전 스타일 Sharepoint 웹 파트 만들기  
 사용자 지정을 만드는 데 Visual Studio에서 서식 파일을 사용할 수 있습니다 [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] SharePoint에 대 한 웹 파트입니다. [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)]웹 파트의 맨 위에 빌드됩니다는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 파트 인프라를 구성 하 고 새 프로젝트에 대해이 좋습니다.  
  
 매우 드문 경우에는 이전 스타일 sharepoint 웹 파트를 사용 하 여 웹 파트를 만들어야 할 수도 있습니다. Visual Studio를 사용 하 여 이러한 종류의 웹 파트를 만들 수 있지만 Visual Studio에 만들 수 있도록 특별히 고안 된 템플릿을 제공 하지 않습니다.  
  
 Sharepoint 웹 파트는 이전 스타일을 만들려고 할 수 있습니다 하는 경우에 대 한 자세한 내용은 참조 [Windows SharePoint Services의 웹 파트 인프라](http://go.microsoft.com/fwlink/?LinkId=169290)합니다. Sharepoint 웹 파트는 이전 스타일을 사용 하 여 웹 파트를 만드는 방법에 대 한 자세한 내용은 참조 [기본 SharePoint 웹 파트를 만드는 연습](http://go.microsoft.com/fwlink/?LinkId=169288)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)|SharePoint 페이지에 대 한 웹 파트를 만드는 방법을 보여 줍니다.|  
|[방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)|SharePoint에 대 한 시각적 디자인 화면을 사용 하 여 웹 파트를 만드는 방법을 보여 줍니다.|  
|[방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|응용 프로그램 페이지 및 SharePoint에서 실행 되는 웹 파트에서 사용할 수 있는 재사용 가능한 사용자 지정 컨트롤을 만드는 방법을 보여 줍니다.|  
|[연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)|SharePoint에 대 한 웹 파트를 디자인 하는 방법에 설명 합니다.|  
|[연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)|시각적 디자인 화면에 컨트롤을 끌어 for SharePoint 웹 파트를 디자인 하는 방법에 설명 합니다.|  
|[연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)|Silverlight 응용 프로그램을 호스트 하 고 SharePoint 목록에서 데이터를 표시 하는 SharePoint에 대 한 웹 파트를 디자인 하는 방법에 설명 합니다.|  
  
  