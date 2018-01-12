---
title: "연습: 사용자 지정 마스터 페이지를 가져오고 사이트 페이지를 이미지로 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 544c3c727046fdcabcde90f221f4b630c11cf29f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-import-a-custom-master-page-and-site-page-with-an-image"></a>연습: 사용자 지정 마스터 페이지 및 사이트 페이지를 이미지로 가져오기
  이 연습에서는 SharePoint 사용자 지정 마스터 페이지 및 사이트 페이지에 이미지를 가져오는 방법에는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트.  
  
 이 연습에서는 다음 작업을 수행 하는 방법을 보여 줍니다.  
  
-   SharePoint Designer에서 이미지를 사용 하 여 사용자 지정 마스터 페이지와 사이트 페이지를 만듭니다.  
  
-   SharePoint 솔루션 (.wsp) 파일에 사용자 지정 마스터 페이지, 이미지 및 사이트 페이지를 내보냅니다.  
  
-   가져와서.wsp 파일을 배포는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 솔루션 패키지 가져오기 프로젝트를 사용 하 여 SharePoint 프로젝트.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료 하려면 다음 구성 요소가 있어야 합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][SharePoint 솔루션 개발을 위한 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
-   SharePoint Designer 2010입니다.  
  
## <a name="create-items-in-sharepoint-designer"></a>SharePoint Designer에 항목 만들기  
 이 예제에는 내보내기에 대 한 SharePoint Designer에서 세 가지 항목을 만드는 방법을 보여 줍니다: 사용자 지정 마스터 페이지, 사용자 지정 마스터 페이지 및 사이트 페이지에 표시할 이미지 파일을 참조 하는 사이트 페이지입니다. 이미지는 SharePoint에서 /images/ 폴더에 추가 됩니다.  
  
#### <a name="to-create-a-custom-master-page-in-sharepoint-designer"></a>SharePoint Designer에서 사용자 지정 마스터 페이지를 만들려면  
  
1.  SharePoint 디자이너의 탐색 창에서 선택 합니다는 **마스터 페이지** 사이트 개체입니다.  
  
2.  에 **마스터 페이지** 리본에서 선택 **빈 마스터 페이지**합니다.  
  
3.  새 마스터 페이지를 선택를 선택한 후는 **마스터 페이지** 리본에서 선택 **파일 편집**합니다.  
  
4.  SharePoint Designer의 맨 아래에 선택 된 **코드** 탭 합니다.  
  
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
  
6.  페이지를 저장, 선택는 **마스터 페이지** 탭을으로 마스터 페이지 이름 바꾸기 **mybasic1.master**합니다.  
  
## <a name="add-an-image-to-the-content-database-in-sharepoint-designer"></a>SharePoint Designer에서 콘텐츠 데이터베이스에 이미지 추가  
 이제 사이트 페이지에 표시할 이미지를 추가할 수 있습니다. 이미지는 SharePoint 콘텐츠 데이터베이스에 배포 됩니다.  
  
#### <a name="to-add-an-image-to-the-content-database-in-sharepoint-designer"></a>SharePoint Designer에서 콘텐츠 데이터베이스에 이미지를 추가 하려면  
  
1.  탐색 창에서 선택 된 **모든 파일** 사이트 개체를 선택한 다음 메뉴 트리 보기에서는 **이미지** 폴더입니다.  
  
2.  에 **모든 파일** 리본에서 선택 **파일 가져오기**, 사용자가 선택한 파일을 선택한 다음 선택에서 **확인** 단추입니다. 이 예제에서는 파일의 이름은 **myimg1.png**합니다.  
  
     필요에 따라 이미지를 구성 하는 데 도움이 되도록 하위 폴더를 만들 수 있습니다.  
  
3.  닫기는 **가져오기** 대화 상자.  
  
## <a name="create-a-site-page"></a>사이트 페이지 만들기  
 이 기본 사이트 페이지 사용자 지정 마스터 페이지를 사용 하 고 이전 단계에서 추가한 이미지를 표시 합니다.  
  
#### <a name="to-create-a-site-page"></a>사이트 페이지를 만들려면  
  
1.  탐색 창에서 선택 된 **사이트 페이지** 개체입니다.  
  
2.  에 **페이지** 리본에서 선택 된 **페이지** 단추를 선택는 **ASPX** 유형, 페이지 및 다음 새 파일의 이름을 **mycontentpage1.aspx**합니다.  
  
     필요에 따라 사이트 페이지를 구성 하는 데 도움이 되도록 하위 폴더를 만들 수 있습니다.  
  
3.  사이트 페이지 목록에서 선택 **MyContentPage1.aspx** 해당 속성 페이지를 열고 다음 페이지 맨 아래에 선택 하 고 **파일 편집** 링크 합니다.  
  
     메시지 및이 페이지는 안전 모드에서 편집할 수 있는 모든 영역에 포함 되어 있지 않습니다에 따르면 나타나고 고급 모드에서이 페이지를 열고 것인지 여부를 묻는 경우는 **예** 단추입니다.  
  
4.  페이지의 맨 아래에 선택 된 **코드** 단추입니다.  
  
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
  
6.  업데이트 된 사이트 페이지를 저장 합니다.  
  
## <a name="export-the-items-from-sharepoint"></a>SharePoint에서 항목 내보내기  
 SharePoint 솔루션 (.wsp) 파일을 SharePoint에서 항목을 내보냅니다.  
  
#### <a name="to-export-items-from-sharepoint-designer"></a>SharePoint Designer에서 항목을 내보내려면  
  
1.  SharePoint 디자이너의 탐색 창에서 선택 합니다는 **팀 사이트** 개체를 선택한 다음는 **사이트** 리본에서 선택 **템플릿으로 저장**합니다.  
  
2.  에 **템플릿으로 저장** 대화 상자에 파일 이름 및 템플릿 이름을 입력 합니다는 **콘텐츠 포함** 확인란을 선택한 후는 **확인** 단추입니다.  
  
     이 사이트의 내용을.wsp 파일에 저장합니다.  
  
3.  솔루션을 내보낸 후에 선택할는 **솔루션 갤러리** 링크를 사용할 수 있는 솔루션 파일의 목록을 표시 합니다.  
  
4.  새.wsp 파일에 대 한 바로 가기 메뉴를 연 다음 선택 **으로 대상 저장** 시스템에 저장 해야 합니다.  
  
## <a name="import-the-items-into-visual-studio"></a>Visual Studio로 가져오기 항목  
 .Wsp 파일을 가져올 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 콘텐츠를 가져온 후 사용자 지정, 더 많은 항목을 추가한 다음 배포 합니다.  
  
#### <a name="to-import-items-from-the-wsp-file-into-visual-studio"></a>Visual Studio에.wsp 파일에서 항목을 가져오려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]을 만듭니다는 **SharePoint 2010 솔루션 패키지 가져오기** 프로젝트.  
  
2.  에 **가져올 항목 선택** 페이지의 **모듈** 에 **형식** 열을 가져오기 위해 다음 표에 파일에 대 한 확인란을 선택 합니다.  
  
    |파일 이름|설명|  
    |---------------|-----------------|  
    |_catalogsmasterpage\_|사용자 지정 마스터 페이지입니다.|  
    |images_|SharePoint 파일 시스템에 이미지 파일입니다.|  
    |SitePages_|사이트 페이지입니다.|  
  
3.  선택의 **마침** 단추를 선택한 항목을 가져옵니다.  
  
4.  **솔루션 탐색기**, 선택는 _catalogsmasterpage\_ 노드를의 값을 설정 하 고 해당 **배포 충돌 해결** 속성을 **자동**합니다.  
  
     이렇게 하면 배포 충돌이 자동으로 확인 됩니다.  
  
5.  기존 페이지와 새 마스터 페이지를 사용 하는 동일한 이름이 기존 페이지는 기본 마스터 페이지 또는 SharePoint Designer에서 사용자 지정 마스터 페이지도 표시 되지 않도록 해야 합니다.  
  
     기존 마스터 페이지 기본 마스터 페이지 또는 사용자 지정 마스터 페이지도 표시 되 면 배포 오류 메시지가 결과로 마스터 페이지를 삭제할 수 없습니다 얻게 됩니다. 이 문제를 방지 하려면이 수행 합니다.  
  
    -   기존 마스터 페이지 (마스터) 페이지 기본 설정 되어 일시적으로 다른 마스터 페이지 기본 마스터 페이지로 설정 합니다. SharePoint에 파일을 배포한 후 새 마스터 페이지를 기본 마스터 페이지로 설정 합니다.  
  
    -   기존 마스터 페이지 사용자 지정 마스터 페이지로 설정 되어 일시적으로 다른 마스터 페이지 사용자 지정 마스터 페이지로 설정 합니다. SharePoint에 파일을 배포한 후 사용자 지정 마스터 페이지와 새 마스터 페이지를 설정 합니다.  
  
6.  메뉴 모음에서 **빌드**, **솔루션 배포**합니다.  
  
7.  배포 항목을 보려면 SharePoint 사이트를 엽니다.  
  
 다른 방법으로 파일을 가져올 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 배포 합니다 SharePoint 파일의 모듈에 추가 하는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][하는 방법: 마스터 페이지 또는 테마 가져오기](../sharepoint/how-to-import-a-master-page-or-theme.md) 및 [모듈을 사용 하 여 솔루션의 파일을 포함 하도록](../sharepoint/using-modules-to-include-files-in-the-solution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  