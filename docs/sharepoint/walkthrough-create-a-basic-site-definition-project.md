---
title: "연습: 기본 사이트 정의 프로젝트 만들기"
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
ms.assetid: b0df5b0e-5fa0-43d8-a339-6d92f1276764
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 연습: 기본 사이트 정의 프로젝트 만들기
  이 연습에서는 일부 컨트롤이 있는 비주얼 웹 파트가 포함된 기본 사이트 정의를 만드는 방법을 보여 줍니다.  구분하기 쉽도록 사용자가 만든 비주얼 웹 파트에는 몇 개의 컨트롤만 있습니다.  하지만 추가 기능이 포함된 보다 복잡한 SharePoint 사이트 정의를 만들 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 템플릿을 사용하여 사이트 정의 만들기  
  
-   SharePoint에서 사이트 정의를 사용하여 SharePoint 사이트 만들기  
  
-   솔루션에 비주얼 웹 파트 추가  
  
-   새로운 비주얼 웹 파트를 추가하여 사이트의 default.aspx 페이지 사용자 지정  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  자세한 내용은 SharePoint 솔루션 개발 요구 사항을 참조하십시오.  
  
-   Visual Studio  
  
## 사이트 정의 솔루션 만들기  
 먼저 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사이트 정의를 만듭니다.  
  
#### 사이트 정의 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  IDE가 Visual Basic 개발 설정을 사용하도록 설정된 경우, 메뉴 표시줄에서 **파일**, **새 프로젝트** 를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  **Visual C\#** 노드 또는 **Visual Basic** 노드를 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
3.  **템플릿** 리스트에서 **SharePoint 2010 프로젝트** 템플릿을 선택합니다.  
  
4.  **이름** 상자에 TestSiteDef를 입력한 후 **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
5.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 사이트 정의를 디버깅할 SharePoint 사이트의 URL을 입력하거나 기본 위치\(http:\/\/*System Name*\/\)를 사용합니다.  
  
6.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택합니다.  
  
     모든 사이트 정의 프로젝트를 팜 솔루션으로 배포해야 합니다.  샌드박스가 적용된 솔루션과 팜 솔루션 비교에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
7.  **마침** 단추를 선택합니다.  
  
     **솔루션 탐색기**에 프로젝트가 나타납니다.  
  
8.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 메뉴 모음에서 **프로젝트**, **화면 추가**를 선택합니다.  
  
9. **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
10. **템플릿** 창에서 **사이트 정의** 템플릿을 선택하고 **이름** 을 **SiteDefinition1** 로 입력한 후 **추가** 버튼을 선택합니다.  
  
## 비주얼 웹 파트 만들기  
 다음으로, 사이트 정의의 기본 페이지에 표시할 비주얼 웹 파트를 만듭니다.  
  
#### 비주얼 웹 파트를 만들려면  
  
1.  **솔루션 탐색기**에서 **모든 파일 표시** 버튼을 선택합니다.  
  
2.  **SiteDefinition1** 프로젝트 노드를 선택한 후, 메뉴 표시줄에서 **프로젝트**, **새 항목 추가** 를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
3.  **Visual C\#** 노드 또는 **Visual Basic** 노드를 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  템플릿 목록에서 **비주얼 웹 파트** 템플릿을 선택하고, 기본 이름값을 VisualWebPart1로 지정한 후, **추가** 버튼을 선택합니다.  
  
     VisualWebPart1.ascx 파일이 열립니다.  
  
5.  VisualWebPart1.ascx의 맨 아래에 다음 태그를 추가하여 텍스트 상자, 단추, 레이블의 세 컨트롤을 폼에 추가합니다.  
  
    ```  
    <table>  
      <tr>  
        <td>  
          <asp:TextBox runat="server" ID="tbName"></asp:TextBox>  
        </td>  
        <td>  
          <asp:Button runat="server" ID="btnSubmit" Text = "Change Label Text" OnClick="btnSubmit_Click"></asp:Button>  
        </td>  
        <td>  
          <asp:Label runat="server" ID="lblName"></asp:Label>  
        </td>  
      </tr>  
    </table>  
    ```  
  
6.  VisualWebPart1.ascx 아래에 있는 VisualWebPart1.ascx.cs\([!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]의 경우\) 또는 VisualWebPart1.ascx.vb\([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]의 경우\) 파일을 열고 다음 코드를 추가합니다.  
  
     [!code-csharp[SP_SimpleSiteDef#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_simplesitedef/cs/testsitedef/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]
     [!code-vb[SP_SimpleSiteDef#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_simplesitedef/vb/testsitedefvb/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]  
  
     이 코드는 웹 파트의 단추 클릭에 대한 기능을 추가합니다.  
  
## 기본 ASPX 페이지에 비주얼 웹 파트 추가  
 다음으로, 사이트 정의의 기본 ASPX 페이지에 비주얼 웹 파트를 추가합니다.  
  
#### 기본 ASPX 페이지에 비주얼 웹 파트를 추가하려면  
  
1.  default.aspx 페이지를 열고 `WebPartPages` 태그 아래에 다음 줄을 추가합니다.  
  
    ```  
    <%@ Register Tagprefix="MyWebPartControls" Namespace="TestSiteDef.VisualWebPart1" Assembly="$SharePoint.Project.AssemblyFullName$" %>  
    ```  
  
     이 줄에서는 MyWebPartControls라는 이름을 웹 파트 및 해당 코드에 연결합니다.  *Namespace* 매개 변수는 VisualWebPart1.ascx 코드 파일에 사용 되는 네임 스페이스와 매치합니다.  
  
2.  `</asp:Content>` 요소 뒤에서 전체 `ContentPlaceHolderId="PlaceHolderMain"` 섹션과 그 내용을 다음 코드로 바꿉니다.  
  
    ```  
    <asp:Content ID="Content1" ContentPlaceHolderId="PlaceHolderMain" runat="server">  
        <MyWebPartControls:VisualWebPart1 runat="server" />      
    </asp:Content>  
    ```  
  
     이 코드는 앞에서 만든 비주얼 웹 파트에 대한 참조를 만듭니다.  
  
3.  **솔루션 탐색기**에서 **SiteDefinition1** 노드에 대한 바로 가기 메뉴를 열고 **시작 항목으로 설정**을 선택합니다.  
  
## 사이트 정의 솔루션 배포 및 실행  
 다음으로, 프로젝트를 SharePoint에 배포하고 프로젝트를 실행 합니다.  
  
#### 사이트 정의를 배포 및 실행하려면  
  
-   메뉴 모음에서 **빌드**, **TestSiteDef 배포**를 선택합니다.  
  
-   F5 키를 선택합니다.  
  
     Visual Studio에서 코드를 컴파일하고, 기능을 추가하고, 모든 파일을 SharePoint solution \(WSP\) 파일로 패키징한 다음 WSP 파일을 SharePoint Server에 배포합니다.  그러면 SharePoint에서 파일을 설치하고 기능을 활성화합니다.  
  
## 사이트 정의를 기반으로 하여 사이트 만들기  
 다음으로, 새 사이트 정의를 사용하여 사이트를 만듭니다.  
  
#### 사이트 정의를 사용하여 사이트를 만들려면  
  
1.  SharePoint 사이트에 새 SharePoint 사이트 페이지가 나타납니다.  
  
2.  **제목 및 설명** 섹션에서 사이트의 제목과 설명으로 My New Site를 입력합니다.  
  
3.  **웹 사이트 주소** 섹션의 **URL 이름** 상자에 mynewsite를 입력합니다.  
  
4.  **템플릿** 섹션에서 **SharePoint 사용자 지정** 탭을 선택합니다.  
  
5.  **템플릿 선택** 목록에서 **SiteDefinition1** 을 선택합니다.  
  
6.  다른 설정은 기본값으로 두고 **만들기** 버튼을 선택합니다.  
  
     새 사이트가 나타납니다.  
  
## 새 사이트 테스트  
 다음으로, 새 사이트를 테스트하여 제대로 작동하는지 확인합니다.  
  
#### 새 사이트를 테스트하려면  
  
-   기본 ASPX 페이지에 일부 텍스트를 입력한 다음, 텍스트 상자 옆에 있는 **레이블 텍스트 변경** 버튼을 선택합니다.  
  
     버튼 오른쪽에 있는 레이블에 해당 텍스트가 표시됩니다.  
  
## 참고 항목  
 [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  