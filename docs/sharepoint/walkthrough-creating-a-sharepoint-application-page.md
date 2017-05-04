---
title: "연습: SharePoint 응용 프로그램 페이지 만들기 | Microsoft Docs"
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
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 개발"
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 만들기"
ms.assetid: 5b6dd941-5c59-4a89-89d0-8e973a00ae9e
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# 연습: SharePoint 응용 프로그램 페이지 만들기
  응용 프로그램 페이지는 특수한 형태의 ASP.NET 페이지입니다.  응용 프로그램 페이지에는 SharePoint 마스터 페이지와 병합되는 콘텐츠가 포함되어 있습니다.  자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)을 참조하십시오.  
  
 이 연습에서는 응용 프로그램 페이지를 만든 다음 로컬 SharePoint 사이트를 사용하여 이 페이지를 디버깅하는 방법을 보여 줍니다.  이 페이지에는 각 사용자가 서버 팜의 모든 사이트에서 만들었거나 수정한 모든 항목이 표시됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint 프로젝트 만들기  
  
-   SharePoint 프로젝트에 응용 프로그램 페이지 추가  
  
-   응용 프로그램 페이지에 ASP.NET 컨트롤 추가  
  
-   ASP.NET 컨트롤의 코드 숨김 파일 추가  
  
-   응용 프로그램 페이지 테스트  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)] 또는 Visual Studio Ultimate 또는 Visual Studio Premium  
  
## SharePoint 프로젝트 만들기  
 먼저 **빈 SharePoint 프로젝트**를 만듭니다.  나중에 이 프로젝트에 **응용 프로그램 페이지** 항목을 추가합니다.  
  
#### SharePoint 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  **새 프로젝트** 대화 상자를 열고 사용할 언어 아래의 **Office\/SharePoint** 노드를 확장한 다음 **SharePoint Solutions** 노드를 선택합니다.  
  
3.  **Visual Studio에 설치되어 있는 템플릿** 창에서 **SharePoint 2010 – 빈 프로젝트** 템플릿을 선택합니다.  프로젝트 MySharePointProject의 이름을 지정한 다음 **확인** 단추를 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  이 마법사를 사용하면 프로젝트를 디버깅하는 데 사용할 사이트와 솔루션의 신뢰 수준을 선택할 수 있습니다.  
  
4.  **팜 솔루션으로 배포** 옵션 단추를 선택한 다음 **마침** 단추를 선택하여 기본 로컬 SharePoint 사이트를 사용합니다.  
  
## 응용 프로그램 페이지 만들기  
 응용 프로그램 페이지를 만들려면 프로젝트에 **응용 프로그램 페이지** 항목을 추가합니다.  
  
#### 응용 프로그램 페이지를 만들려면  
  
1.  **솔루션 탐색기**에서 **MySharePointProject** 프로젝트를 선택합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **응용 프로그램 페이지\(팜 솔루션에만 해당\)** 템플릿을 선택합니다.  
  
4.  페이지 이름을 SearchItems로 지정한 다음 **추가** 단추를 선택합니다.  
  
     Visual Web Developer 디자이너의 **소스**  뷰에 응용 프로그램 페이지가 표시되며 여기서 페이지의 HTML 요소를 볼 수 있습니다.  디자이너에 여러 <xref:System.Web.UI.WebControls.Content> 컨트롤의 태그가 표시됩니다.  각 컨트롤은 기본 응용 프로그램 마스터 페이지에 정의되어 있는 <xref:System.Web.UI.WebControls.ContentPlaceHolder> 컨트롤에 매핑됩니다.  
  
## 응용 프로그램 페이지의 레이아웃 디자인  
 응용 프로그램 페이지 항목을 추가하면 디자이너를 사용하여 응용 프로그램 페이지에 ASP.NET 컨트롤을 추가할 수 있습니다.  이 디자이너는 Visual Web Developer에서 사용되는 디자이너와 같습니다.  표준 ASP.NET 페이지를 디자인할 때와 같은 방식으로 레이블, 라디오 단추 목록 및 표를 디자이너의 **소스** 뷰에 추가한 다음 속성을 설정할 수 있습니다.  
  
 Visual Web Developer의 디자이너를 사용하는 방법에 대한 자세한 내용은 [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)을 참조하십시오.  
  
#### 응용 프로그램 페이지의 레이아웃을 디자인하려면  
  
1.  메뉴 모음에서 **보기**, **도구 상자**를 선택합니다.  
  
2.  **도구 상자** 표준 노드에서 다음 단계 중 하나를 수행합니다.  
  
    -   **라벨** 항목 바로 가기 메뉴를 열고 **복사**를 선택하고, 디자이너의 **PlaceHolderMain** 콘텐츠 컨트롤 아래 라인에서 바로 가기 메뉴를 연 다음 **붙여넣기**를 선택합니다.  
  
    -   **도구 상자**의 **레이블** 항목을 **PlaceHolderMain** 콘텐츠 컨트롤로 끌어 옵니다.  
  
3.  이전 단계를 반복해서 **DropDownList** 항목 및 **Table** 항목을 **PlaceHolderMain** 콘텐츠 컨트롤에 추가합니다.  
  
4.  디자이너에서 레이블 컨트롤의 `Text` 특성 값을 모든 항목 표시로 변경합니다.  
  
5.  디자이너에서 `<asp:DropDownList>` 요소를 다음 XML로 바꿉니다.  
  
    ```  
    <asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"  
     OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">  
        <asp:ListItem Text="Created by me" Value="Author"></asp:ListItem>  
        <asp:ListItem Text="Modified by me" Value="Editor"></asp:ListItem>  
    </asp:DropDownList>  
    ```  
  
## 페이지에 있는 컨트롤의 이벤트 처리  
 ASP.NET 페이지와 같은 방식으로 응용 프로그램 페이지의 컨트롤을 처리합니다.  이 절차에서는 드롭다운 목록의 `SelectedIndexChanged`이벤트를 처리합니다.  
  
#### 페이지에 있는 컨트롤의 이벤트를 처리하려면  
  
1.  **보기** 메뉴에서 **코드**를 선택합니다.  
  
     코드 편집기에서 응용 프로그램 페이지 코드 파일이 열립니다.  
  
2.  `SearchItems` 클래스에 다음 메서드를 추가합니다.  이 코드는 이 연습의 뒷부분에서 만들 메서드를 호출하여 <xref:System.Web.UI.WebControls.DropDownList>의 <xref:System.Web.UI.WebControls.ListControl.SelectedIndexChanged> 이벤트를 처리합니다.  
  
     [!code-csharp[SP_ApplicationPage#5](../snippets/csharp/VS_Snippets_OfficeSP/sp_applicationpage/cs/layouts/sp_applicationpage/SearchItems.aspx.cs#5)]
     [!code-vb[SP_ApplicationPage#5](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_applicationpage/vb/layouts/sp_applicationpage/SearchItems.aspx.vb#5)]  
  
3.  응용 프로그램 페이지 코드 파일의 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[SP_ApplicationPage#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_applicationpage/cs/layouts/sp_applicationpage/SearchItems.aspx.cs#1)]
     [!code-vb[SP_ApplicationPage#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_applicationpage/vb/layouts/sp_applicationpage/SearchItems.aspx.vb#1)]  
  
4.  `SearchItems` 클래스에 다음 메서드를 추가합니다.  이 메서드는 서버 팜의 모든 사이트를 반복하여 현재 사용자가 만들거나 수정한 항목을 검색합니다.  
  
     [!code-csharp[SP_ApplicationPage#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_applicationpage/cs/layouts/sp_applicationpage/SearchItems.aspx.cs#2)]
     [!code-vb[SP_ApplicationPage#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_applicationpage/vb/layouts/sp_applicationpage/SearchItems.aspx.vb#2)]  
  
5.  `SearchItems` 클래스에 다음 메서드를 추가합니다.  이 메서드는 현재 사용자가 테이블에서 만들거나 수정한 항목을 표시합니다.  
  
     [!code-csharp[SP_ApplicationPage#3](../snippets/csharp/VS_Snippets_OfficeSP/sp_applicationpage/cs/layouts/sp_applicationpage/SearchItems.aspx.cs#3)]
     [!code-vb[SP_ApplicationPage#3](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_applicationpage/vb/layouts/sp_applicationpage/SearchItems.aspx.vb#3)]  
  
## 응용 프로그램 페이지 테스트  
 프로젝트를 실행하면 SharePoint 사이트가 열리고 응용 프로그램 페이지가 표시됩니다.  
  
#### 응용 프로그램 페이지를 테스트하려면  
  
1.  **솔루션 탐색기**에서 응용 프로그램 페이지의 바로 가기 메뉴를 연 후 **시작 항목으로 설정**을 선택합니다.  
  
2.  F5 키를 선택합니다.  
  
     SharePoint 사이트가 열립니다.  
  
3.  응용 프로그램 페이지에서 **내가 수정한 문서** 옵션을 선택합니다.  
  
     응용 프로그램 페이지가 새로 고쳐지고 현재 사용자가 서버 팜의 모든 사이트에서 수정한 항목이 모두 표시됩니다.  
  
4.  응용 프로그램 페이지의 목록에서 **내가 만듦**을 선택합니다.  
  
     응용 프로그램 페이지가 새로 고쳐지고 현재 사용자가 서버 팜의 모든 사이트에서 만든 항목이 모두 표시됩니다.  
  
## 다음 단계  
 SharePoint 응용 프로그램 페이지에 대한 자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)를 참조하십시오.  
  
 다음 항목에서 Visual Web Designer를 사용하여 SharePoint 페이지 콘텐츠를 디자인하는 방법에 대해 더 자세히 알아볼 수 있습니다.  
  
-   [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
-   [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
## 참고 항목  
 [방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md)   
 [응용 프로그램 \_layouts 페이지 형식](http://go.microsoft.com/fwlink/?LinkID=169274)  
  
  