---
title: "연습: Outlook 양식 영역 디자인"
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
  - "양식 영역[Visual Studio에서 Office 개발], 만들기"
ms.assetid: b033fc06-cdeb-4d7f-804b-86d15bfa022a
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 연습: Outlook 양식 영역 디자인
  사용자 지정 양식 영역은 표준 또는 사용자 지정 Microsoft Office Outlook 양식을 확장합니다.  이 연습에서는 연락처 항목의 검사기 창에 새 페이지로 표시되는 사용자 지정 양식 영역을 디자인합니다.  이 양식 영역은 Windows Live 로컬 검색 웹 사이트에 주소 정보를 전송하여 연락처에 대해 나열된 각 주소의 지도를 표시합니다.  양식 영역에 대한 자세한 내용은 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   새 Outlook VSTO 추가 기능 프로젝트 만들기  
  
-   VSTO 추가 기능 프로젝트에 양식 영역 추가  
  
-   양식 영역의 레이아웃 디자인  
  
-   양식 영역의 동작 사용자 지정  
  
-   Outlook 양식 영역 테스트  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] 또는 [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)]  
  
 ![비디오에 링크](~/data-tools/media/playvideo.gif "비디오에 링크") 이 항목의 동영상 버전은 [동영상 방법: Outlook 양식 영역 디자인](http://go.microsoft.com/fwlink/?LinkID=140824)\(영문\)을 참조하세요.  
  
## 새 Outlook VSTO 추가 기능 프로젝트 만들기  
 먼저 기본 VSTO 추가 기능 프로젝트를 만듭니다.  
  
#### 새 Outlook VSTO 추가 기능 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 이름이 MapItAddIn인 Outlook VSTO 추가 기능 프로젝트를 만듭니다.  
  
2.  **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기**를 선택합니다.  
  
3.  임의 디렉터리에 프로젝트를 저장합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
## Outlook VSTO 추가 기능 프로젝트에 양식 영역 추가  
 Outlook VSTO 추가 기능 솔루션에는 하나 이상의 Outlook 양식 영역 항목이 포함될 수 있습니다.  **새 Outlook 양식 영역** 마법사를 사용하여 프로젝트에 양식 영역 항목을 추가합니다.  
  
#### Outlook VSTO 추가 기능 프로젝트에 양식 영역을 추가하려면  
  
1.  **솔루션 탐색기**에서 **MapItAddIn** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **Outlook 양식 영역**을 선택하고 파일 이름을 MapIt로 지정한 다음 **추가**를 클릭합니다.  
  
     **새Outlook 양식 영역** 마법사가 시작됩니다.  
  
4.  **양식 영역을 만드는 방법 선택** 페이지에서 **새 양식 영역 디자인**을 클릭한 후 **다음**을 클릭합니다.  
  
5.  **만들 양식 영역 형식 선택** 페이지에서 **별도**를 클릭한 후 **다음**을 클릭합니다.  
  
     *별도* 양식 영역은 Outlook 양식에 새 페이지를 추가합니다.  양식 영역 형식에 대한 자세한 내용은 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
6.  **설명 텍스트를 입력하고 디스플레이 기본 설정을 선택하세요.** 페이지의 **이름** 상자에 **Map It**을 입력합니다.  
  
     이 이름은 연락처 항목이 열려 있을 때 검사기 창의 리본 메뉴에 나타납니다.  
  
7.  **작성 모드의 검사기** 및 **읽기 모드의 검사기**를 선택하고 **다음**을 클릭합니다.  
  
8.  **이 양식 영역을 표시할 메시지 클래스를 지정하세요.** 페이지에서 **메일 메시지**를 선택 취소하고 **연락처**를 선택한 다음 **마침**을 클릭합니다.  
  
     MapIt.cs 또는 MapIt.vb 파일이 프로젝트에 추가됩니다.  
  
## 양식 영역의 레이아웃 디자인  
 *양식 영역 디자이너*를 사용하여 시각적으로 양식 영역을 개발합니다.  관리되는 컨트롤을 양식 영역 디자이너 화면으로 끌 수 있습니다.  디자이너 및 **속성** 창을 사용하여 컨트롤 레이아웃 및 모양을 조정합니다.  
  
#### 양식 영역의 레이아웃을 디자인하려면  
  
1.  **솔루션 탐색기**에서 **MapItAddIn** 프로젝트를 확장하고 MapIt.cs 또는 MapIt.vb를 두 번 클릭하여 양식 영역 디자이너를 엽니다.  
  
2.  디자이너를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
3.  **속성** 창에서 **크기**를 664, 469로 설정합니다.  
  
     이렇게 하면 양식 영역이 지도를 표시할 수 있을 만큼 커집니다.  
  
4.  **보기** 메뉴에서 **도구 상자**를 클릭합니다.  
  
5.  **도구 상자**의 **공용 컨트롤** 탭에서 양식 영역에 **WebBrowser**를 추가합니다.  
  
     **WebBrowser**에 연락처에 대해 나열된 각 주소의 지도가 표시됩니다.  
  
## 양식 영역의 동작 사용자 지정  
 양식 영역 이벤트 처리기에 코드를 추가하여 런타임에 양식 영역이 동작하는 방식을 사용자 지정합니다.  이 양식 영역에 대해 코드에서 Outlook 항목의 속성을 검사하고 Map It 양식 영역을 표시할지 여부를 확인합니다.  양식 영역을 표시하는 경우 코드에서 Windows Live 로컬 검색으로 이동하고 Outlook 연락처 항목에 나열된 각 주소의 지도를 로드합니다.  
  
#### 양식 영역의 동작을 사용자 지정하려면  
  
1.  **솔루션 탐색기**에서 MapIt.cs 또는 MapIt.vb를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
     MapIt.cs 또는 MapIt.vb가 코드 편집기에서 열립니다.  
  
2.  **양식 영역 팩터리** 코드 영역을 확장합니다.  
  
     `MapItFactory`라는 양식 영역 팩터리 클래스가 노출됩니다.  
  
3.  다음 코드를 `MapItFactory_FormRegionInitializing` 이벤트 처리기에 추가합니다.  이 이벤트 처리기는 사용자가 연락처 항목을 열 때 호출됩니다.  다음 코드는 연락처 항목에 주소가 포함되어 있는지 여부를 확인합니다.  연락처 항목에 주소가 포함되어 있지 않으면 이 코드에서 <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> 클래스의 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 **true**로 설정하며 양식 영역이 표시되지 않습니다.  그렇지 않은 경우 VSTO 추가 기능에서 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 이벤트가 발생하고 양식 영역이 표시됩니다.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/CS/MapIt.cs#1)]
     [!code-vb[Trin_Outlook_FR_Separate#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/VB/MapIt.vb#1)]  
  
4.  다음 코드를 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 이벤트 처리기에 추가합니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   연락처 항목의 각 주소를 연결하고 URL 문자열을 만듭니다.  
  
    -   <xref:System.Windows.Forms.WebBrowser> 개체의 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드를 호출하고 URL 문자열을 매개 변수로 전달합니다.  
  
     로컬 검색 웹 사이트가 Map It 양식 영역에 나타나고 각 주소를 스크래치 패드에 표시합니다.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/CS/MapIt.cs#2)]
     [!code-vb[Trin_Outlook_FR_Separate#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/VB/MapIt.vb#2)]  
  
## Outlook 양식 영역 테스트  
 프로젝트를 실행하면 Visual Studio에서 Outlook을 엽니다.  연락처 항목을 열어 Map It 양식 영역을 표시합니다.  Map It 양식 영역은 주소가 포함된 연락처 항목의 양식에 페이지로 표시됩니다.  
  
#### Map It 양식 영역을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
     Outlook이 열립니다.  
  
2.  Outlook의 **홈** 탭에서 **새 항목**을 클릭한 다음 **연락처**를 클릭합니다.  
  
3.  연락처 양식에서 **Ann Beebe**를 연락처 이름으로 입력하고 다음 세 개의 주소를 지정합니다.  
  
    |주소 형식|주소|  
    |-----------|--------|  
    |**비즈니스**|4567 Main St.  Buffalo, NY|  
    |**홈**|1234 North St.  Buffalo, NY|  
    |**기타**|3456 Main St.  Seattle, WA|  
  
4.  연락처 항목을 저장하고 닫습니다.  
  
5.  **Ann Beebe** 연락처 항목을 다시 엽니다.  
  
6.  항목 리본 메뉴의 **표시** 그룹에서 **Map It**을 클릭하여 Map It 양식 영역을 엽니다.  
  
     Map It 양식 영역이 나타나고 로컬 검색 웹 사이트를 표시합니다.  **비즈니스**, **홈** 및 **기타** 주소가 스크래치 패드에 나타납니다.  스크래치 패드에서 매핑할 주소를 선택합니다.  
  
## 다음 단계  
 다음 항목에서 Outlook 응용 프로그램의 UI를 사용자 지정하는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   Outlook 항목의 리본 메뉴를 사용자 지정하는 방법에 대해 알아보려면 [Outlook에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)을 참조하세요.  
  
## 참고 항목  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [연습: Outlook에서 디자인한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)   
 [방법: Outlook에서 양식 영역 표시하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  