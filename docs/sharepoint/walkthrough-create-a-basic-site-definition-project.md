---
title: "연습: 기본 사이트 정의 프로젝트 만들기 | Microsoft Docs"
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
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
ms.assetid: b0df5b0e-5fa0-43d8-a339-6d92f1276764
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9bea8fec27b0d53fb1cfe3405d39d271a93f5a8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-basic-site-definition-project"></a>연습: 기본 사이트 정의 프로젝트 만들기
  이 연습에서는 일부 컨트롤에 비주얼 웹 파트를 포함 하는 기본 사이트 정의 만드는 방법을 보여 줍니다. 명확 하 게 설명를 만들면 비주얼 웹 파트 컨트롤 몇 가지에 있습니다. 그러나 더 많은 기능을 포함 하는 보다 복잡 한 SharePoint 사이트 정의 만들 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용 하 여 사이트 정의 만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 서식 파일 프로젝트.  
  
-   SharePoint에서 사이트 정의 사용 하 여 SharePoint 사이트를 만듭니다.  
  
-   비주얼 웹 파트를 솔루션에 추가 합니다.  
  
-   새 비주얼 웹 파트를 추가 하 여 사이트의 default.aspx 페이지를 사용자 지정 합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. 자세한 내용은 SharePoint 솔루션 개발에 대 한 요구 사항을 참조 합니다.  
  
-   Visual Studio.  
  
## <a name="creating-a-site-definition-solution"></a>사이트 정의 솔루션 만들기  
 사이트 정의 프로젝트를 먼저 만듭니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
#### <a name="to-create-a-site-definition-project"></a>사이트 정의 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다. IDE에는 메뉴 모음에서 Visual Basic 개발 설정을 사용 하도록 설정 된, 선택 **파일**, **새 프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  확장은 **Visual C#** 노드 또는 **Visual Basic** 노드를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
3.  에 **템플릿** 목록에서 선택 된 **SharePoint 2010 프로젝트** 서식 파일.  
  
4.  에 **이름** 상자에 입력 **TestSiteDef**, 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 사이트 정의 디버그 하려면 SharePoint 사이트에 대 한 URL을 입력 하거나 기본 위치를 사용 하 여 (http://*시스템 이름*/).  
  
6.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 선택 된 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
     모든 사이트 정의 프로젝트 팜 솔루션으로 배포 되어야 합니다. 샌드박스 솔루션과 팜 솔루션 비교에 대 한 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
7.  선택 된 **마침** 단추입니다.  
  
     에 프로젝트가 표시 **솔루션 탐색기**합니다.  
  
8.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
9. 아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
10. 에 **템플릿** 창 선택는 **사이트 정의** 서식 파일을 두십시오는 **이름** 으로 **SiteDefinition1**는 를선택합니다 **추가** 단추입니다.  
  
## <a name="create-a-visual-web-part"></a>비주얼 웹 파트 만들기  
 다음으로 사이트 정의 기본 페이지에 표시할 비주얼 웹 파트를 만듭니다.  
  
#### <a name="to-create-a-visual-web-part"></a>비주얼 웹 파트를 만들려면  
  
1.  **솔루션 탐색기**, 선택는 **모든 파일 표시** 단추입니다.  
  
2.  선택 된 **SiteDefinition1** 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
3.  확장은 **Visual C#** 노드 또는 **Visual Basic** 노드를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  템플릿 목록에서 선택 된 **비주얼 웹 파트** 템플릿, 기본 VisualWebPart1, 이름을 지정 하 고 다음을 선택 하는 유지는 **추가** 단추입니다.  
  
     VisualWebPart1.ascx 파일이 열립니다.  
  
5.  VisualWebPart1.ascx 맨 아래에 세 개의 컨트롤을 폼에 추가 하려면 다음 태그를 추가: 텍스트 상자, 단추 및 레이블:  
  
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
  
6.  VisualWebPart1.ascx, 아래에서 VisualWebPart1.ascx.cs 파일을 엽니다 (에 대 한 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]) 또는 VisualWebPart1.ascx.vb (에 대 한 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]), 다음 코드를 추가 합니다.  
  
     [!code-vb[SP_SimpleSiteDef#1](../sharepoint/codesnippet/VisualBasic/testsitedefvb/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_SimpleSiteDef#1](../sharepoint/codesnippet/CSharp/testsitedef/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]  
  
     이 코드는 웹 파트의 단추 클릭에 대 한 기능을 추가 합니다.  
  
## <a name="add-the-visual-web-part-to-the-default-aspx-page"></a>기본 ASPX 페이지에 비주얼 웹 파트 추가  
 다음으로, 사이트 정의 기본 ASPX 페이지에 비주얼 웹 파트를 추가 합니다.  
  
#### <a name="to-add-a-visual-web-part-to-the-default-aspx-page"></a>기본 ASPX 페이지에 비주얼 웹 파트를 추가 하려면  
  
1.  Default.aspx 페이지를 열고 아래에 다음 줄을 추가 합니다는 `WebPartPages` 태그:  
  
    ```  
    <%@ Register Tagprefix="MyWebPartControls" Namespace="TestSiteDef.VisualWebPart1" Assembly="$SharePoint.Project.AssemblyFullName$" %>  
    ```  
  
     이 줄 웹 파트와 코드 MyWebPartControls 이름을 연결 합니다. *Namespace* 매개 변수와 일치 VisualWebPart1.ascx 코드 파일에 사용 되는 네임 스페이스입니다.  
  
2.  이후에 `</asp:Content>` 요소 전체를 바꿉니다 `ContentPlaceHolderId="PlaceHolderMain"` 섹션과 그 내용을 다음 코드로:  
  
    ```  
    <asp:Content ID="Content1" ContentPlaceHolderId="PlaceHolderMain" runat="server">  
        <MyWebPartControls:VisualWebPart1 runat="server" />      
    </asp:Content>  
    ```  
  
     이 코드는 앞에서 만든 비주얼 웹 파트에 대 한 참조를 만듭니다.  
  
3.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SiteDefinition1** 노드를 선택한 후 **시작 항목으로 설정**합니다.  
  
## <a name="deploy-and-run-the-site-definition-solution"></a>사이트 정의 솔루션 배포 및 실행  
 다음으로 프로젝트를 SharePoint에 배포 하 고 프로젝트를 실행 하십시오.  
  
#### <a name="to-deploy-and-run-the-site-definition"></a>사이트 정의를 배포 및 실행하려면  
  
-   메뉴 모음에서 **빌드**, **배포 TestSiteDef**합니다.  
  
-   F5 키를 선택 합니다.  
  
     Visual Studio 코드를 컴파일하, 해당 기능을 추가, SharePoint 솔루션 (WSP) 파일에 패키지의 모든 파일 및 WSP 파일을 SharePoint 서버에 배포 합니다. SharePoint 다음 파일을 설치 하 고 기능을 활성화 합니다.  
  
## <a name="create-a-site-based-on-the-site-definition"></a>사이트 정의에 따라 사이트 만들기  
 다음으로 새 사이트 정의 사용 하 여 사이트를 만듭니다.  
  
#### <a name="to-create-a-site-by-using-the-site-definition"></a>사이트 정의 사용 하 여 사이트를 만들려면  
  
1.  SharePoint 사이트에서 새 SharePoint 사이트 페이지가 표시 됩니다.  
  
2.  에 **제목 및 설명** 섹션에서 입력 **My New Site** 제목 및 사이트의 설명에 대 한 합니다.  
  
3.  에 **웹 사이트 주소** 섹션에서 입력 **mynewsite** 에 **URL 이름** 상자입니다.  
  
4.  에 **템플릿** 섹션에서 선택 된 **SharePoint 사용자 지정** 탭 합니다.  
  
5.  에 **´ ï ´** 목록에서 선택 **SiteDefinition1**합니다.  
  
6.  다른 설정을 해당 기본값으로 둡니다 선택한 후는 **만들기** 단추입니다.  
  
     새 사이트가 나타납니다.  
  
## <a name="test-the-new-site"></a>새 사이트를 테스트 합니다.  
 다음으로 올바르게 작동 하는지 확인 하려면 새 사이트를 테스트 합니다.  
  
#### <a name="to-test-the-new-site"></a>새 사이트를 테스트 하려면  
  
-   기본 ASPX 페이지에 텍스트를 입력 한 다음 선택에서 **레이블 텍스트 변경** 텍스트 상자 옆에 있는 단추입니다.  
  
     텍스트 레이블 단추의 오른쪽에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  