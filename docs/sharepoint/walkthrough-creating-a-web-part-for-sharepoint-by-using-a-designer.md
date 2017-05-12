---
title: "연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기"
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
  - "웹 파트[Visual Studio에서 SharePoint 개발], 만들기"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 디자이너"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 디자인"
ms.assetid: 3dd62654-ada2-468f-b7da-eb5704a2ff7a
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# 연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기
  SharePoint 사이트를 위해 웹 파트를 만드는 경우 사용자가 해당 사이트 페이지의 콘텐츠, 모양 및 동작을 브라우저에서 직접 수정할 수 있습니다.  이 연습에서는[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint **비주얼 웹 파트** 프로젝트 템플릿을 사용하여 시각적으로 웹 파트를 만드는 방법을 보여 줍니다.  
  
 만들려는 웹 파트는 월별 달력 보기와 사이트의 각 달력 목록에 대한 확인란을 표시합니다.  사용자는 확인란을 선택하여 월별 달력 보기에 포함할 달력 목록을 지정할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   **비주얼 웹 파트** 프로젝트 템플릿을 사용하여 웹 파트 만들기  
  
-   Visual Studio의 Visual Web Developer 디자이너를 사용하여 웹 파트 디자인  
  
-   웹 파트에 있는 컨트롤의 이벤트를 처리하기 위한 코드 추가  
  
-   SharePoint에서 웹 파트 테스트  
  
    > [!NOTE]  
    >  시스템에서 Visual Studio 사용자 인터페이스의 일부 요소에 대해 다음 지침에서 설명한 것과 다른 이름 또는 위치를 표시할 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)를 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Windows 및 SharePoint 버전.  [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)를 참조하십시오.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)] 이상.  
  
## 웹 파트 프로젝트 만들기  
 먼저 **비주얼 웹 파트** 프로젝트 템플릿을 사용하여 웹 파트 프로젝트를 만듭니다.  
  
#### 비주얼 웹 파트 프로젝트를 만들려면  
  
1.  **관리자 권한으로 실행** 옵션을 사용하여 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
3.  **새 프로젝트** 대화 상자의 **Visual C\#** 또는 **Visual Basic**에서 **Office\/SharePoint** 를 확장하고 나서 **Office\/SharePoint** 범주를 선택합니다.  
  
4.  템플릿 목록에서, **SharePoint 2013 \- Visual Web Part** 템플릿을 선택하고 나서 **확인** 단추를 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  이 마법사를 사용하면 프로젝트를 디버깅하는 데 사용할 사이트와 솔루션의 신뢰 수준을 지정할 수 있습니다.  
  
5.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택합니다.  
  
6.  **마침** 단추를 선택하여 기본 로컬 SharePoint 사이트를 수락합니다.  
  
## 웹 파트 디자인  
 **도구**  상자의 컨트롤을 Visual Web Developer 디자이너에 추가하여 웹 파트를 디자인합니다.  
  
#### 웹 파트의 레이아웃을 디자인하려면  
  
1.  Visual Web Developer 디자이너에서 **디자인** 탭을 선택하여 디자인 뷰로 전환합니다.  
  
2.  메뉴 모음에서 **보기**, **도구 상자**를 선택합니다.  
  
3.  **도구 상자**의 **표준** 노드에서, **CheckBoxList** 컨트롤을 선택하고 나서 다음 단계 중 하나를 수행합니다.  
  
    -   **CheckBoxList** 컨트롤을 위해 바로 가기 메뉴를 열고 **복사**를 선택한 다음 디자이너의 첫 번째 줄에서 바로 가기 메뉴를 열고 나서 **붙여넣기**를 선택합니다.  
  
    -   **도구 상자**의 **CheckBoxList** 컨트롤을 끌어와서 디자이너의 첫 번째 줄에 연결합니다.  
  
4.  이전 단계를 반복하지만 단추를 디자이너의 다음 줄으로 이동합니다.  
  
5.  디자이너에서 **Button1** 단추를 선택합니다.  
  
6.  메뉴 모음에서 **보기**, **속성 창**을 선택합니다.  
  
     **속성** 창이 열립니다.  
  
7.  단추의 **텍스트** 속성에 업데이트를 입력합니다.  
  
## 웹 파트에 있는 컨트롤의 이벤트 처리  
 사용자가 마스터 달력 보기에 달력을 추가할 수 있게 해 주는 코드를 추가합니다.  
  
#### 웹 파트에 있는 컨트롤의 이벤트를 처리하려면  
  
1.  다음 단계 중 하나를 수행합니다.  
  
    -   디자이너에서 **Update** 단추를 두 번 클릭합니다.  
  
    -   **업데이트** 단추의 **속성** 창에서 **이벤트** 단추를 선택합니다.  **클릭** 속성에 **Button1\_Click**을 입력한 다음 Enter 키를 선택합니다.  
  
     코드 편집기에서 사용자 정의 컨트롤 코드 파일이 열리고 `Button1_Click` 이벤트 처리기가 나타납니다.  나중에 이 이벤트 처리기에 코드를 추가합니다.  
  
2.  사용자 정의 컨트롤 코드 파일의 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[SP_VisualWebPart#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_visualwebpart/cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]
     [!code-vb[SP_VisualWebPart#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_visualwebpart/vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]  
  
3.  다음 코드 줄을 `VisualWebPart1` 클래스에 추가합니다.  이 코드는 월별 달력 보기 컨트롤을 선언합니다.  
  
     [!code-csharp[SP_VisualWebPart#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_visualwebpart/cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#2)]
     [!code-vb[SP_VisualWebPart#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_visualwebpart/vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#2)]  
  
4.  `VisualWebPart1` 클래스의 `Page_Load` 메서드를 다음 코드로 바꿉니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   월별 달력 보기를 사용자 정의 컨트롤에 추가합니다.  
  
    -   사이트의 각 달력 목록에 대한 확인란을 추가합니다.  
  
    -   달력 보기에 표시되는 각 항목 형식에 대한 템플릿을 지정합니다.  
  
     [!code-csharp[SP_VisualWebPart#3](../snippets/csharp/VS_Snippets_OfficeSP/sp_visualwebpart/cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#3)]
     [!code-vb[SP_VisualWebPart#3](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_visualwebpart/vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#3)]  
  
5.  `VisualWebPart1` 클래스의 `Button1_Click` 메서드를 다음 코드로 바꿉니다.  이 코드는 선택한 각 달력의 항목을 마스터 달력 보기에 추가합니다.  
  
     [!code-csharp[SP_VisualWebPart#4](../snippets/csharp/VS_Snippets_OfficeSP/sp_visualwebpart/cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#4)]
     [!code-vb[SP_VisualWebPart#4](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_visualwebpart/vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#4)]  
  
## 웹 파트 테스트  
 프로젝트를 실행하면 SharePoint 사이트가 열립니다.  웹 파트는 SharePoint의 웹 파트 갤러리에 자동으로 추가됩니다.  이 프로젝트를 테스트하려면 다음 작업을 수행합니다.  
  
-   별개의 두 달력 목록에 각각 이벤트를 추가합니다.  
  
-   웹 파트 페이지에 웹 파트를 추가합니다.  
  
-   월별 달력 보기에 포함할 목록을 지정합니다.  
  
#### 사이트의 달력 목록에 이벤트를 추가하려면  
  
1.  Visual Studio에서 F5 키를 선택합니다.  
  
     SharePoint 사이트가 열리고 페이지에 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 빠른 실행 모음이 표시됩니다.  
  
2.  빠른 실행 모음의 **목록**에서 **달력** 링크를 선택합니다.  
  
     **달력** 페이지가 나타납니다.  
  
     빠른 실행 모음에 일정 링크가 나타나면 **사이트 내용** 링크를 선택합니다.  사이트 콘텐츠 페이지에 **일정** 항목이 표시되지 않으면 일정 항목을 만듭니다.  
  
3.  캘린더 페이지에서 날짜를 선택하고 나서 이벤트 추가로 선택된 날짜에 **추가** 링크를 선택합니다.  
  
4.  **제목** 상자에 Event in the default calendar를 입력한 다음 **저장** 단추를 선택합니다.  
  
5.  **사이트 내용**을 선택한 다음 **응용 프로그램 추가** 타일을 선택합니다.  
  
6.  **만들기** 페이지에서 **일정** 형식을 선택하고 일정 이름을 지정한 다음 **만들기** 단추를 선택합니다.  
  
7.  새 달력에 이벤트를 추가하고, 사용자 지정 달력에서 이벤트 이름을 지정한 다음, **저장** 단추를 선택합니다.  
  
#### 웹 파트 페이지에 웹 파트를 추가하려면  
  
1.  **사이트 내용** 페이지에서 **사이트 페이지** 폴더를 엽니다.  
  
2.  리본 메뉴에서 **파일** 탭을 선택하고 **새 문서** 메뉴를 열고 나서 **웹 파트 페이지** 명령어를 선택합니다.  
  
3.  **새 웹 파트 페이지** 페이지에서 페이지 이름으로 **SampleWebPartPage.aspx**를 지정한 다음 **만들기**를 선택합니다.  
  
     웹 파트 페이지가 표시됩니다.  
  
4.  웹 파트 페이지 상단에서, **삽입** 탭을 선택하고 나서 **웹 파트** 단추를 선택합니다.  
  
5.  **사용자 지정** 폴더를 선택하고 **VisualWebPart1** 웹 파트를 선택한 다음 **추가**를 선택합니다.  
  
     페이지에 웹 파트 페이지가 표시됩니다.  웹 파트에 다음 컨트롤이 표시됩니다.  
  
    -   월별 달력 보기  
  
    -   **Update** 단추  
  
    -   **Calendar** 확인란  
  
    -   **Custom Calendar** 확인란  
  
#### 월별 달력 보기에 포함할 목록을 지정하려면  
  
1.  웹 파트에서 월별 달력 보기에 포함할 달력을 지정한 다음 **업데이트** 단추를 선택합니다.  
  
     지정한 모든 달력의 이벤트가 월별 달력 보기에 표시됩니다.  
  
## 참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)   
 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)  
  
  