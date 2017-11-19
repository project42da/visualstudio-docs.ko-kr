---
title: "연습: 디자이너를 사용 하 여 SharePoint를 위한 웹 파트 만들기 | Microsoft Docs"
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
- Web Parts [SharePoint development in Visual Studio], designer
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
ms.assetid: 3dd62654-ada2-468f-b7da-eb5704a2ff7a
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 55da85b9740216cefe55911d79dab2c16b035695
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer"></a>연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기
  SharePoint 사이트에 대 한 웹 파트를 만드는 경우 사용자가 직접 수정할 수 콘텐츠, 모양 및 동작 해당 사이트의 페이지는 브라우저를 사용 하 여 합니다. 이 연습에서는 SharePoint를 사용 하 여 웹 파트를 시각적으로 만드는 방법을 보여 줍니다. **비주얼 웹 파트** 프로젝트 템플릿을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
 사이트의 월별 달력 보기 및 각 일정 목록에 대 한 확인란이 표시 하는 웹 파트를 만듭니다. 확인란을 선택 하 여 월별 달력 보기에 포함할 달력 목록을 사용자 지정할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용 하 여 웹 파트를 만드는 **비주얼 웹 파트** 서식 파일 프로젝트.  
  
-   Visual Studio에서 Visual Web Developer 디자이너를 사용 하 여 웹 파트를 디자인 합니다.  
  
-   웹 파트에 있는 컨트롤의 이벤트를 처리 하는 코드를 추가 합니다.  
  
-   Sharepoint에서 웹 파트를 테스트 합니다.  
  
    > [!NOTE]  
    >  컴퓨터는 다음 지침에 설명 된 다른 이름이 나 for Visual Studio 사용자 인터페이스의 몇 가지 요소에 대 한 위치 표시 될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Windows 및 SharePoint 버전의 지원. 참조 [SharePoint 솔루션 개발을 위한 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]이상이 필요 합니다.  
  
## <a name="creating-a-web-part-project"></a>웹 파트 프로젝트 만들기  
 먼저, 사용 하 여 웹 파트 프로젝트를 만들는 **비주얼 웹 파트** 프로젝트 템플릿을 합니다.  
  
#### <a name="to-create-a-visual-web-part-project"></a>비주얼 웹 파트 프로젝트를 만들려면  
  
1.  시작 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 를 사용 하 여는 **관리자 권한으로 실행** 옵션입니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 아래에서 **Visual C#** 또는 **Visual Basic**, 확장 **Office/SharePoint**는 선택 **SharePoint 솔루션** 범주입니다.  
  
4.  템플릿 목록에서 선택 된 **SharePoint 2013-비주얼 웹 파트** 서식 파일을 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다. 이 마법사를 사용 하 여 사이트를 사용 하 여 프로젝트와 솔루션의 신뢰 수준을 디버그를 지정할 수 있습니다.  
  
5.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 선택 된 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
6.  선택 된 **마침** 단추 기본 로컬 SharePoint 사이트를 허용 하도록 합니다.  
  
## <a name="designing-the-web-part"></a>웹 파트 디자인  
 웹 파트 컨트롤을 추가 하 여 디자인 된 **도구 상자** Visual Web Developer 디자이너의 화면으로 합니다.  
  
#### <a name="to-design-the-layout-of-the-web-part"></a>웹 파트의 레이아웃을 디자인 하려면  
  
1.  Visual Web Developer 디자이너에서 선택 된 **디자인** 디자인 뷰로 전환 하려면 탭 합니다.  
  
2.  메뉴 모음에서 **보기**, **도구 상자**를 차례로 선택합니다.  
  
3.  에 **표준** 의 노드는 **도구 상자**, 선택는 **CheckBoxList** 컨트롤을 다음 단계 중 하나를 수행 합니다.  
  
    -   에 대 한 바로 가기 메뉴를 열고는 **CheckBoxList** 컨트롤을 선택 **복사**를 디자이너에서 첫 번째 줄에 대 한 바로 가기 메뉴를 열고 다음 선택 **붙여넣기**합니다.  
  
    -   끌어서는 **CheckBoxList** 에서 제어는 **도구 상자**, 컨트롤 디자이너에서 첫 번째 줄에 연결 합니다.  
  
4.  이전 단계를 반복 하지만 단추는 디자이너의 다음 줄으로 이동 합니다.  
  
5.  디자이너에서 선택 된 **Button1** 단추입니다.  
  
6.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
     **속성** 창이 열립니다.  
  
7.  에 **텍스트** 단추의 속성 입력 **업데이트**합니다.  
  
## <a name="handling-the-events-of-controls-on-the-web-part"></a>웹 파트에 있는 컨트롤의 이벤트 처리  
 사용자가 마스터 일정 보기에 일정을 추가할 수 있도록 하는 코드를 추가 합니다.  
  
#### <a name="to-handle-events-of-controls-on-the-web-part"></a>웹 파트에 있는 컨트롤의 이벤트를 처리 하려면  
  
1.  다음 단계 중 하나를 수행합니다.  
  
    -   디자이너에서 두 번 클릭 하 여 **업데이트** 단추입니다.  
  
    -   에 **속성** 창에는 **업데이트** 단추를 선택는 **이벤트** 단추입니다. 에 **클릭** 속성을 입력 **Button1_Click**, Enter 키를 선택 합니다.  
  
     사용자 제어 코드 파일이 코드 편집기에서 열립니다 및 `Button1_Click` 이벤트 처리기가 나타납니다. 이상 버전에서는이 이벤트 처리기에 코드를 추가 합니다.  
  
2.  사용자 정의 컨트롤 코드 파일의 맨 위에 다음 문을 추가 합니다.  
  
     [!code-vb[SP_VisualWebPart#1](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_VisualWebPart#1](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]  
  
3.  다음 줄의 코드를 추가 `VisualWebPart1` 클래스입니다. 이 코드는 월별 달력 보기 컨트롤을 선언합니다.  
  
     [!code-vb[SP_VisualWebPart#2](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#2)]
     [!code-csharp[SP_VisualWebPart#2](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#2)]  
  
4.  대체는 `Page_Load` 의 메서드는 `VisualWebPart1` 를 다음 코드로 클래스입니다. 이 코드는 다음 작업을 수행합니다.  
  
    -   사용자 정의 컨트롤에 월별 달력 보기를 추가합니다.  
  
    -   사이트에서 각 일정 목록에 대 한 확인란을 추가합니다.  
  
    -   달력 보기에 표시 되는 항목의 각 형식에 대 한 서식 파일을 지정 합니다.  
  
     [!code-vb[SP_VisualWebPart#3](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#3)]
     [!code-csharp[SP_VisualWebPart#3](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#3)]  
  
5.  대체는 `Button1_Click` 의 메서드는 `VisualWebPart1` 를 다음 코드로 클래스입니다. 이 코드 마스터 달력 보기에 선택 된 각 달력에서 항목을 추가합니다.  
  
     [!code-vb[SP_VisualWebPart#4](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#4)]
     [!code-csharp[SP_VisualWebPart#4](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#4)]  
  
## <a name="testing-the-web-part"></a>웹 파트 테스트  
 프로젝트를 실행 하는 경우 SharePoint 사이트가 열립니다. 웹 파트는 sharepoint에서 웹 파트 갤러리에 자동으로 추가 됩니다. 이 프로젝트를 테스트 하려면 다음 작업을 수행 합니다.  
  
-   이벤트를 각각 두 개의 별도 일정 목록에 추가 합니다.  
  
-   웹 파트 페이지에 웹 파트를 추가 합니다.  
  
-   월별 일정 보기에 포함할 목록을 지정 합니다.  
  
#### <a name="to-add-events-to-calendar-lists-on-the-site"></a>사이트에서 달력 목록에 이벤트를 추가 하려면  
  
1.  Visual Studio에서 F5 키를 선택 합니다.  
  
     SharePoint 사이트가 열리면 및 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 빠른 실행 표시줄 페이지에 나타납니다.  
  
2.  빠른 실행 표시줄에서 아래 **나열**, 선택는 **달력** 링크 합니다.  
  
     **달력** 페이지가 나타납니다.  
  
     달력 링크가 없는 나타나면 빠른 실행 표시줄에, 선택는 **사이트 콘텐츠** 링크 합니다. 사이트 내용 페이지에 표시 되지 않으면는 **달력** 항목을 하나 만듭니다.  
  
3.  일정 페이지에서 하루를 선택 하 고 선택 된 **추가** 이벤트 추가 하려면 선택한 날에 링크 합니다.  
  
4.  에 **제목** 상자에 입력 **기본 달력에서 이벤트**, 선택한 후는 **저장** 단추입니다.  
  
5.  선택 된 **사이트 콘텐츠** 링크를 선택한 다음 선택는 **앱 추가** 바둑판식으로 배열 합니다.  
  
6.  에 **만들기** 페이지를 선택 합니다는 **달력** 입력 일정의 이름 지정 하 고 선택 합니다는 **만들기** 단추입니다.  
  
7.  새 일정에 이벤트를 추가, 이벤트 이름을 **사용자 지정 달력에서 이벤트**, 선택한 후는 **저장** 단추입니다.  
  
#### <a name="to-add-the-web-part-to-a-web-part-page"></a>웹 파트 페이지에 웹 파트를 추가 하려면  
  
1.  에 **사이트 콘텐츠** 페이지를 열고는 **사이트 페이지** 폴더입니다.  
  
2.  리본에서 선택는 **파일** 탭을 열고는 **새 문서** 메뉴를 선택한 후는 **웹 파트 페이지** 명령입니다.  
  
3.  에 **새 웹 파트 페이지** 페이지에서 페이지의 이름을 **SampleWebPartPage.aspx**를 선택한 후는 **만들기** 단추입니다.  
  
     웹 파트 페이지가 나타납니다.  
  
4.  웹 파트 페이지의 위쪽 영역에서 선택 된 **삽입** 탭을 선택 합니다는 **웹 파트** 단추입니다.  
  
5.  선택 된 **사용자 지정** 폴더를 선택는 **VisualWebPart1** 웹 파트를 선택한 후는 **추가** 단추입니다.  
  
     웹 파트 페이지에 나타납니다. 웹 파트에는 다음과 같은 컨트롤이 표시 됩니다.  
  
    -   월별 일정 보기입니다.  
  
    -   **업데이트** 단추입니다.  
  
    -   A **달력** 확인란 합니다.  
  
    -   A **사용자 지정 달력** 확인란 합니다.  
  
#### <a name="to-specify-lists-to-include-in-the-monthly-calendar-view"></a>월별 일정 보기에 포함 하도록 목록을 지정 하려면  
  
1.  웹 파트에서 다음을 선택 하 고 월별 달력 보기에 포함할 원하는 일정을 지정 된 **업데이트** 단추입니다.  
  
     사용자가 지정한 모든 일정의 이벤트는 월별 일정 보기에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)   
 [방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)  
  
  