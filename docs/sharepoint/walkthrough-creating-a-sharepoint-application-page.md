---
title: "연습: SharePoint 응용 프로그램 페이지 만들기 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
ms.assetid: 5b6dd941-5c59-4a89-89d0-8e973a00ae9e
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e49e8d50905dc0bb0b3c104a7133fe7435e2e944
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-sharepoint-application-page"></a>연습: SharePoint 응용 프로그램 페이지 만들기
  응용 프로그램 페이지에는 ASP.NET 페이지의 특수 한 형태입니다. 응용 프로그램 페이지에는 SharePoint 마스터 페이지와 병합 되는 콘텐츠가 포함 됩니다. 자세한 내용은 참조 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)합니다.  
  
 이 연습에서는 응용 프로그램 페이지를 만들고 다음 로컬 SharePoint 사이트를 사용 하 여 디버깅 하는 방법을 보여 줍니다. 이 페이지에는 각 사용자가 생성 또는 서버 팜의 모든 사이트에서 수정 하는 모든 항목이 표시 됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint 프로젝트를 만듭니다.  
  
-   SharePoint 프로젝트에 응용 프로그램 페이지를 추가 합니다.  
  
-   응용 프로그램 페이지에 ASP.NET 컨트롤을 추가 합니다.  
  
-   ASP.NET 컨트롤 뒤에 있는 코드를 추가 합니다.  
  
-   응용 프로그램 페이지를 테스트 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Windows 및 SharePoint 버전의 지원. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]또는 Visual Studio Ultimate 또는 Visual Studio Premium 버전을 지정 합니다.  
  
## <a name="creating-a-sharepoint-project"></a>SharePoint 프로젝트 만들기  
 먼저 만듭니다는 **빈 SharePoint 프로젝트**합니다. 추가한 나중는 **응용 프로그램 페이지** 이 프로젝트에 대 한 항목입니다.  
  
#### <a name="to-create-a-sharepoint-project"></a>SharePoint 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  열기는 **새 프로젝트** 대화 상자에서 **Office/SharePoint** 를 선택 하 고 사용할 언어 아래의 노드는 **SharePoint 솔루션** 노드.  
  
3.  에 **Visual Studio 설치 된 템플릿** 창에서 선택 된 **SharePoint 2010-빈 프로젝트** 서식 파일. 프로젝트 이름을 **MySharePointProject**를 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다. 이 마법사를 사용 하면 프로젝트 및 솔루션의 신뢰 수준을 디버깅 하는 데 사용할 사이트를 선택할 수 있습니다.  
  
4.  선택의 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 단추 기본 로컬 SharePoint 사이트를 허용 하도록 합니다.  
  
## <a name="creating-an-application-page"></a>응용 프로그램 페이지 만들기  
 응용 프로그램 페이지를 만들려면 추가 **응용 프로그램 페이지** 항목을 프로젝트입니다.  
  
#### <a name="to-create-an-application-page"></a>응용 프로그램 페이지를 만들려면  
  
1.  **솔루션 탐색기**, 선택는 **MySharePointProject** 프로젝트.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 선택 하는 **응용 프로그램 페이지 (팜 솔루션에만** 템플릿.  
  
4.  페이지 이름을 **SearchItems**를 선택한 후는 **추가** 단추입니다.  
  
     Visual Web Developer 디자이너의 응용 프로그램 페이지를 표시 **소스** 보기 페이지의 HTML 요소를 볼 수 있습니다. 디자이너는 여러 태그를 표시 <xref:System.Web.UI.WebControls.Content> 컨트롤입니다. 각 컨트롤에 매핑되는 <xref:System.Web.UI.WebControls.ContentPlaceHolder> 기본 응용 프로그램 마스터 페이지에 정의 된 컨트롤입니다.  
  
## <a name="designing-the-layout-of-the-application-page"></a>응용 프로그램 페이지의 레이아웃 디자인  
 응용 프로그램 페이지 항목을 사용 하는 디자이너를 사용 하 여 응용 프로그램 페이지에 ASP.NET 컨트롤을 추가할 수 있습니다. 이 디자이너는 Visual Web Developer에서 사용 되는 동일한 디자이너입니다. 레이블, 라디오 단추 목록 및 테이블을 추가 **소스** 디자이너, 보기 및 표준 ASP.NET 페이지를 디자인할 때와 마찬가지로 다음 속성을 설정 합니다.  
  
#### <a name="to-design-the-layout-of-the-application-page"></a>응용 프로그램 페이지의 레이아웃을 디자인  
  
1.  메뉴 모음에서 **보기**, **도구 상자**를 차례로 선택합니다.  
  
2.  표준 노드에 **도구 상자**, 다음 단계 중 하나를 수행 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **레이블** 항목을 선택 **복사**, 아래의 줄에 대 한 바로 가기 메뉴를 열고는 **PlaceHolderMain** 콘텐츠 디자이너에서 컨트롤을 선택한 다음 선택 **붙여넣기**합니다.  
  
    -   끌어서는 **레이블** 에서 항목의 **도구 상자** 의 본문에는 **PlaceHolderMain** 콘텐츠 컨트롤을 합니다.  
  
3.  추가 하려면 이전 단계를 반복 하는 **DropDownList** 항목 및 **테이블** 항목의 **PlaceHolderMain** 콘텐츠 컨트롤을 합니다.  
  
4.  디자이너에서의 값을 변경는 `Text` 레이블 컨트롤의 특성 **모든 항목 표시**합니다.  
  
5.  디자이너에서 대체는 `<asp:DropDownList>` 다음 xml 요소입니다.  
  
    ```  
    <asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"  
     OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">  
        <asp:ListItem Text="Created by me" Value="Author"></asp:ListItem>  
        <asp:ListItem Text="Modified by me" Value="Editor"></asp:ListItem>  
    </asp:DropDownList>  
    ```  
  
## <a name="handling-the-events-of-controls-on-the-page"></a>페이지에 있는 컨트롤의 이벤트 처리  
 ASP.NET 페이지와 마찬가지로 응용 프로그램 페이지의 컨트롤을 처리 합니다. 이 절차에서는 처리 합니다는 `SelectedIndexChanged` 드롭 다운 목록의 이벤트입니다.  
  
#### <a name="to-handle-the-events-of-controls-on-the-page"></a>페이지에 있는 컨트롤의 이벤트를 처리 하려면  
  
1.  에 **보기** 메뉴 선택 **코드**합니다.  
  
     응용 프로그램 페이지 코드 파일이 코드 편집기에서 열립니다.  
  
2.  다음 메서드를 `SearchItems` 클래스에 추가합니다. 이 코드에서는 처리는 <xref:System.Web.UI.WebControls.ListControl.SelectedIndexChanged> 의 이벤트는 <xref:System.Web.UI.WebControls.DropDownList> 이 연습의 뒷부분에서 만들어야 하는 메서드를 호출 하 여 합니다.  
  
     [!code-vb[SP_ApplicationPage#5](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#5)]
     [!code-csharp[SP_ApplicationPage#5](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#5)]  
  
3.  응용 프로그램 페이지 코드 파일의 맨 위에 다음 문을 추가 합니다.  
  
     [!code-vb[SP_ApplicationPage#1](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#1)]
     [!code-csharp[SP_ApplicationPage#1](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#1)]  
  
4.  다음 메서드를 `SearchItems` 클래스에 추가합니다. 이 메서드는 서버 팜의 모든 사이트를 반복 하 고 현재 사용자가 만들거나 수정한 항목에 대 한 검색 합니다.  
  
     [!code-vb[SP_ApplicationPage#2](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#2)]
     [!code-csharp[SP_ApplicationPage#2](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#2)]  
  
5.  다음 메서드를 `SearchItems` 클래스에 추가합니다. 이 메서드는 만들거나 수정한 테이블의 현재 사용자가 항목을 표시 합니다.  
  
     [!code-vb[SP_ApplicationPage#3](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#3)]
     [!code-csharp[SP_ApplicationPage#3](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#3)]  
  
## <a name="testing-the-application-page"></a>응용 프로그램 페이지를 테스트합니다.  
 프로젝트를 실행 하는 경우 SharePoint 사이트 열리고 응용 프로그램 페이지가 나타납니다.  
  
#### <a name="to-test-the-application-page"></a>응용 프로그램 페이지를 테스트 하려면  
  
1.  **솔루션 탐색기**를 응용 프로그램 페이지에 대 한 바로 가기 메뉴를 열고 다음 선택 **시작 항목으로 설정**합니다.  
  
2.  F5 키를 선택 합니다.  
  
     SharePoint 사이트가 열립니다.  
  
3.  응용 프로그램 페이지에서 선택 된 **내가 수정** 옵션입니다.  
  
     응용 프로그램 페이지를 새로 고치고 서버 팜의 모든 사이트에서 수정 된 모든 항목이 표시 됩니다.  
  
4.  응용 프로그램 페이지에서 선택 **내가 만든** 목록에 있습니다.  
  
     응용 프로그램 페이지 및 사용자가 만든 서버 팜의 모든 사이트에서 모든 항목이 표시 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 SharePoint 응용 프로그램 페이지에 대 한 자세한 내용은 참조 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)합니다.  
  
 다음이 항목에서 비주얼 웹 디자이너를 사용 하 여 SharePoint 페이지 콘텐츠를 디자인 하는 방법에 대 한 더 알아볼 수 있습니다.  
  
-   [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)합니다.  
  
-   [웹 파트 또는 응용 프로그램 페이지에 대 한 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md)   
 [응용 프로그램 _layouts 유형 페이지](http://go.microsoft.com/fwlink/?LinkID=169274)  
  
  