---
title: "연습: 사용자 지정 마스터 페이지 및 사이트 페이지를 이미지로 가져오기 | Microsoft Docs"
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
  - "항목 가져오기[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 항목 가져오기"
ms.assetid: d1703957-81e2-47e1-b4ca-6a8d550d8da2
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 연습: 사용자 지정 마스터 페이지 및 사이트 페이지를 이미지로 가져오기
  이 연습에서는 SharePoint 사용자 지정 마스터 페이지와 이미지가 있는 사이트 페이지를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트로 가져오는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
-   SharePoint Designer에서 이미지를 사용하여 사용자 지정 마스터 페이지와 사이트 페이지를 만듭니다.  
  
-   사용자 지정 마스터 페이지, 이미지 및 사이트 페이지를 SharePoint 솔루션 파일\(.wsp\)로 내보냅니다.  
  
-   SharePoint 솔루션 패키지 가져오기 프로젝트를 사용하여 .wsp 파일을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트로 가져오고 배포합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio  
  
-   SharePoint Designer 2010  
  
## SharePoint Designer에서 항목 만들기  
 이 예제에서는 내보내기 위해 SharePoint Designer에서 사용자 지정 마스터 페이지, 사용자 지정 마스터 페이지를 참조하는 사이트 페이지 및 사이트 페이지에 나타날 이미지 파일을 만드는 방법을 보여 줍니다.  이미지는 SharePoint에서 \/images\/ 폴더에 추가됩니다.  
  
#### SharePoint Designer에서 사용자 지정 마스터 페이지를 만들려면  
  
1.  SharePoint Designer의 탐색 창에서 **마스터 페이지** 사이트 개체를 선택합니다.  
  
2.  **마스터 페이지** 리본 메뉴에서 **빈 마스터 페이지** 를 선택합니다.  
  
3.  새 마스터 페이지를 선택한 다음 **마스터 페이지** 리본 메뉴에서 **파일 편집** 을 선택합니다.  
  
4.  SharePoint Designer의 아래쪽에서 **코드** 탭을 선택합니다.  
  
5.  기존 태그를 다음 태그로 바꿉니다.  
  
    ```  
    <%@ Master Language="C#" %>  
    <%@ Register tagprefix="SharePoint" namespace="Microsoft.SharePoint.WebControls" assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <html dir="ltr">  
    <head runat="server">  
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">  
    <SharePoint:RobotsMetaTag runat="server" __designer:Preview="" __designer:Values="<P N='InDesign' T='False' /><P N='ID' T='ctl00' /><P N='Page' ID='1' /><P N='TemplateControl' ID='2' /><P N='AppRelativeTemplateSourceDirectory' R='-1' />"></SharePoint:RobotsMetaTag>  
    <title>Web Page</title>  
    </head>  
    <body>  
    <form id="form1" runat="server">  
    <asp:ContentPlaceHolder id="ContentPlaceHolderMain"   
            runat="server">  
          </asp:ContentPlaceHolder>  
    </form>  
    </body>  
    </html>  
    ```  
  
6.  페이지 저장하고 **마스터 페이지** 탭을 선택한 다음 마스터 페이지의 이름을 **mybasic1.master** 로 변경합니다.  
  
## SharePoint Designer에서 콘텐츠 데이터베이스에 이미지 추가  
 이제 사이트 페이지에 표시할 이미지를 추가할 수 있습니다.  이미지가 SharePoint 콘텐츠 데이터베이스에 배포됩니다.  
  
#### SharePoint Designer에서 콘텐츠 데이터베이스에 이미지를 추가하려면  
  
1.  탐색 창에서 **모든 파일** 사이트 개체를 선택한 다음, 트리 뷰에서 **이미지** 폴더를 선택합니다.  
  
2.  **모든 파일** 리본 메뉴에서 **파일 가져오기** 를 선택하고, 원하는 파일을 선택한 다음, **확인** 버튼을 선택합니다.  이 예제에서 파일의 이름은 **myimg1.png**입니다.  
  
     이미지를 구성하는 데 도움이 되도록 하위 폴더를 만들 수도 있습니다.  
  
3.  **가져오기** 대화 상자를 닫습니다.  
  
## 사이트 페이지 만들기  
 이 기본 사이트 페이지에서는 사용자 지정 마스터 페이지를 사용하고 이전 단계에서 추가한 이미지를 표시합니다.  
  
#### 사이트 페이지를 만들려면  
  
1.  탐색 창에서 **사이트 페이지** 개체를 선택합니다.  
  
2.  **페이지** 리본 메뉴에서 **페이지** 버튼을 선택하고, **ASPX** 페이지 형식을 선택한 다음, 새 파일 이름을 **mycontentpage1.aspx** 로 입력합니다.  
  
     사이트 페이지를 구성하는 데 도움이 되도록 하위 폴더를 만들 수도 있습니다.  
  
3.  사이트 페이지 목록에서 **MyContentPage1.aspx** 를 선택하여 속성 페이지를 연 다음, 페이지의 아래쪽에서 **편집** 링크를 선택합니다.  
  
     이 페이지는 안전 모드에서 편집할 수 있는 영역을 포함 하지 않고 이 페이지를 고급 모드에서 열 것인지 여부를 묻는 메세지가 표시될 경우 **예** 버튼을 선택합니다.  
  
4.  페이지의 아래쪽에서 **코드** 버튼을 선택합니다.  
  
5.  기존 태그를 다음 태그로 바꿉니다.  
  
    ```  
    <%@ Import Namespace="Microsoft.SharePoint.ApplicationPages" %>  
    <%@ Register Tagprefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="asp" Namespace="System.Web.UI" Assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" %>  
    <%@ Import Namespace="Microsoft.SharePoint" %>  
    <%@ Assembly Name="Microsoft.Web.CommandUI, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Page Language="C#" Inherits="Microsoft.SharePoint.WebControls.LayoutsPageBase" MasterPageFile="../_catalogs/masterpage/mybasic1.master" meta:progid="SharePoint.WebPartPage.Document" %>  
  
    <asp:Content ID="Main" ContentPlaceHolderID="ContentPlaceHolderMain" runat="server">  
    <img alt="My Image" longdesc="My image from images folder" src="../images/myimg1.png" />  
    </asp:Content>  
    ```  
  
6.  업데이트된 사이트 페이지를 저장합니다.  
  
## SharePoint에서 항목 내보내기  
 SharePoint에서 항목을 SharePoint 솔루션 파일\(.wsp\)로 내보냅니다.  
  
#### SharePoint Designer에서 항목을 내보내려면  
  
1.  SharePoint Designer의 탐색 창에서 **팀 사이트** 개체를 선택한 다음, **사이트** 리본 메뉴에서 **템플릿으로 저장** 을 선택합니다.  
  
2.  **템플릿으로 저장** 대화 상자에서 파일 이름과 템플릿 이름을 입력하고 **콘텐츠 포함** 확인란을 선택한 다음 **확인** 버튼을 선택합니다.  
  
     사이트의 콘텐츠가 .wsp 파일에 저장됩니다.  
  
3.  솔루션을 내보낸 후 **솔루션 갤러리** 링크를 선택하여 사용 가능한 솔루션 파일의 목록을 표시합니다.  
  
4.  새.wsp 파일에 대 한 바로 가기 메뉴를 연 다음 **다른 이름으로 저장** 을 선택하여 시스템에 저장합니다.  
  
## Visual Studio로 항목 가져오기  
 .wsp 파일을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 로 가져옵니다.  콘텐츠를 가져온 후, 사용자 지정하고, 항목을 더 추가한 다음, 배포합니다.  
  
#### .wsp 파일의 항목을 Visual Studio로 가져오려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **SharePoint 2010 솔루션 패키지 가져오기** 프로젝트를 만듭니다.  
  
2.  **가져올 항목 선택** 페이지의 **형식** 열에 있는 **모듈** 아래에서 다음 표의 파일들을 가져오기 위해 확인 란을 선택합니다.  
  
    |파일 이름|설명|  
    |-----------|--------|  
    |\_catalogsmasterpage\_|사용자 지정 마스터 페이지|  
    |images\_|SharePoint 파일 시스템의 이미지 파일|  
    |SitePages\_|사이트 페이지|  
  
3.  **완료** 버튼을 선택하여 선택된 항목을 가져옵니다.  
  
4.  **솔루션 탐색기**에서 \_catalogsmasterpage\_ 노드를 선택하고 **배포 충돌 해결** 속성 값을 **자동**으로 설정합니다.  
  
     이렇게 하면 배포 충돌이 자동으로 해결됩니다.  
  
5.  새 마스터 페이지의 이름이 기존 페이지의 이름과 같으면 기존 페이지가 SharePoint Designer에서 기본 마스터 페이지나 사용자 지정 마스터 페이지로 표시되지 않도록 합니다.  
  
     기존 마스터 페이지가 기본 마스터 페이지나 사용자 지정 마스터 페이지로 표시된 경우 마스터 페이지를 삭제할 수 없다는 배포 오류가 발생합니다.  이 문제를 방지하려면 다음을 수행합니다.  
  
    -   기존 마스터 페이지가 기본 마스터 페이지로 설정된 경우 임시로 다른 마스터 페이지를 기본 마스터 페이지로 설정합니다.  SharePoint에 파일을 배포한 후 새 마스터 페이지를 기본 마스터 페이지로 설정합니다.  
  
    -   기존 마스터 페이지가 사용자 지정 마스터 페이지로 설정된 경우 임시로 다른 마스터 페이지를 사용자 지정 마스터 페이지로 설정합니다.  SharePoint에 파일을 배포한 후 새 마스터 페이지를 사용자 지정 마스터 페이지로 설정합니다.  
  
6.  메뉴 모음에서 **빌드**, **솔루션 배포**를 선택합니다.  
  
7.  SharePoint 사이트를 열고 배포된 항목을 확인합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 파일을 가져오고 SharePoint에 배포하는 다른 방법은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 파일을 모듈에 추가하는 것입니다.  [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [방법: 마스터 페이지 또는 테마 가져오기](../sharepoint/how-to-import-a-master-page-or-theme.md) 및 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## 참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  