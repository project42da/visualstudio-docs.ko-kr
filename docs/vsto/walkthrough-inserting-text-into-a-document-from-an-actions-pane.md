---
title: "연습: 작업 창에서 문서로 텍스트 삽입"
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
  - "작업 창[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "작업 창[Visual Studio에서 Office 개발], Word에서 만들기"
  - "스마트 문서[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "스마트 문서[Visual Studio에서 Office 개발], Word에서 만들기"
ms.assetid: fd14c896-5737-4a20-94f7-6064b67112c5
caps.latest.revision: 70
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 69
---
# 연습: 작업 창에서 문서로 텍스트 삽입
  이 연습에서는 Microsoft Office Word 문서에서 작업 창을 만드는 방법을 보여 줍니다.  작업 창에는 입력 내용을 수집한 다음 해당 텍스트를 문서에 보내는 두 개의 컨트롤이 들어 있습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   작업 창 컨트롤에서 Windows Forms 컨트롤을 사용하여 인터페이스 디자인  
  
-   응용 프로그램이 열릴 때 작업 창 표시  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  My Basic Actions Pane이라는 이름으로 Word 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Word 문서가 열리고 **My Basic Actions Pane** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 문서에 텍스트 및 책갈피 추가  
 작업 창에서는 텍스트를 문서의 책갈피에 보냅니다.  문서를 디자인하려면 텍스트를 일부 입력하여 기본 형식을 만듭니다.  
  
#### 문서에 텍스트를 추가하려면  
  
1.  Word 문서에 다음 텍스트를 입력합니다.  
  
     2008년 3월 21일  
  
     이름  
  
     주소  
  
     이것은 Word의 기본 작업 창 예제입니다.  
  
 Visual Studio의 **도구 상자**에서 끌어 오거나 Word의 **책갈피** 대화 상자를 사용하는 방법으로 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서에 추가할 수 있습니다.  
  
#### 문서에 Bookmark 컨트롤을 추가하려면  
  
1.  **도구 상자**의 **Word 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서로 끌어 놓습니다.  
  
     **Bookmark 컨트롤 추가** 대화 상자가 나타납니다.  
  
2.  단락 기호를 선택하지 않은 상태에서 **이름**이라는 단어를 선택하고 **확인**을 클릭합니다.  
  
    > [!NOTE]  
    >  단락 기호는 책갈피 외부에 있어야 합니다.  문서에 단락 기호가 표시되지 않으면 **도구** 메뉴를 클릭하고 **Microsoft Office Word 도구**를 가리킨 다음 **옵션**을 클릭합니다.  **보기** 탭을 클릭하고 **옵션** 대화 상자의 **서식 기호** 섹션에서 **단락 기호** 확인란을 선택합니다.  
  
3.  **속성** 창에서 **Bookmark1**의 **Name** 속성을 **showName**으로 변경합니다.  
  
4.  단락 기호를 선택하지 않은 상태에서 **주소**를 선택합니다.  
  
5.  리본 메뉴의 **삽입** 탭에 있는 **연결** 그룹에서 **책갈피**를 클릭합니다.  
  
6.  **책갈피** 대화 상자에서 **책갈피 이름** 상자에 **showAddress**를 입력하고 **추가**를 클릭합니다.  
  
## 작업 창에 컨트롤 추가  
 작업 창 인터페이스를 디자인하려면 작업 창 컨트롤을 프로젝트에 추가한 다음 Windows Forms 컨트롤을 작업 창 컨트롤에 추가합니다.  
  
#### 작업 창 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **My Basic Actions Pane** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**을 클릭하고 컨트롤의 이름을 **InsertTextControl**로 지정한 다음 **추가**를 클릭합니다.  
  
#### 작업 창 컨트롤에 Windows Form 컨트롤을 추가하려면  
  
1.  디자이너에 작업 창 컨트롤이 표시되지 않으면 **InsertTextControl**을 두 번 클릭합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 **Label** 컨트롤을 작업 창 컨트롤로 끌어 놓습니다.  
  
3.  Label 컨트롤의 **Text** 속성을 **Name**으로 변경합니다.  
  
4.  **Textbox** 컨트롤을 작업 창 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**getName**|  
    |**크기**|**130, 20**|  
  
5.  두 번째 **Label** 컨트롤을 작업 창 컨트롤에 추가하고 **Text** 속성을 **Address**로 변경합니다.  
  
6.  두 번째 **Textbox** 컨트롤을 작업 창 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**getAddress**|  
    |**Accepts Return**|**True**|  
    |**Multiline**|**True**|  
    |**크기**|**130, 40**|  
  
7.  **Button** 컨트롤을 작업 창 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**addText**|  
    |**텍스트**|**Insert**|  
  
## 문서에 텍스트를 삽입하는 코드 추가  
 작업 창에서 텍스트 상자의 텍스트를 문서에 있는 적절한 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 삽입하는 코드를 작성합니다.  `Globals` 클래스를 사용하여 작업 창의 컨트롤에서 문서의 컨트롤에 액세스할 수 있습니다.  자세한 내용은 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)을 참조하십시오.  
  
#### 작업 창의 텍스트를 문서의 책갈피에 삽입하려면  
  
1.  **addText** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/InsertTextControl.cs#8)]
     [!code-vb[Trin_VstcoreActionsPaneWord#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/InsertTextControl.vb#8)]  
  
2.  C\#의 경우 단추 클릭에 대해 이벤트 처리기를 추가해야 합니다.  이 코드를 `InsertTextControl` 생성자에서 `IntializeComponent`에 대한 호출 밑에 배치할 수 있습니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/InsertTextControl.cs#9)]  
  
## 작업 창을 표시하는 코드 추가  
 작업 창을 표시하려면 만든 컨트롤을 컨트롤 컬렉션에 추가합니다.  
  
#### 작업 창을 표시하려면  
  
1.  `ThisDocument` 클래스에서 작업 창 컨트롤의 새 인스턴스를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#10)]
     [!code-vb[Trin_VstcoreActionsPaneWord#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#10)]  
  
2.  `ThisDocument`의 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneWord#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#11)]  
  
## 응용 프로그램 테스트  
 문서를 열 때 작업 창이 열리고 단추를 클릭하면 텍스트 상자에 입력된 텍스트가 책갈피에 삽입되는지 확인하기 위해 문서를 테스트합니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  작업 창이 표시되는지 확인합니다.  
  
3.  작업 창의 텍스트 상자에 이름과 주소를 입력하고 **Insert**를 클릭합니다.  
  
## 다음 단계  
 이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   Excel에서 작업 창을 만듭니다.  자세한 내용은 [How to: Add an Actions Pane to Excel Workbooks](http://msdn.microsoft.com/ko-kr/62abfce6-e44f-419d-85d8-26bf59f33872)을 참조하십시오.  
  
-   작업 창의 컨트롤에 데이터를 바인딩합니다.  자세한 내용은 [연습: Word 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)을 참조하십시오.  
  
## 참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [How to: Add an Actions Pane to Excel Workbooks](http://msdn.microsoft.com/ko-kr/62abfce6-e44f-419d-85d8-26bf59f33872)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [책갈피 컨트롤](../vsto/bookmark-control.md)  
  
  