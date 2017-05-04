---
title: "연습: CheckBox 컨트롤을 사용하여 문서 서식 변경 | Microsoft Docs"
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
  - "확인란, Word 문서"
  - "컨트롤[Visual Studio에서 Office 개발], 문서에 추가"
  - "문서[Visual Studio에서 Office 개발], check box 컨트롤"
  - "문서[Visual Studio에서 Office 개발], 서식 지정"
  - "Word 문서, 컨트롤을 사용하여 서식 변경"
ms.assetid: 3740e41d-a57e-43bb-87e7-6e5481ef290b
caps.latest.revision: 70
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 69
---
# 연습: CheckBox 컨트롤을 사용하여 문서 서식 변경
  이 연습에서는 Microsoft Office Word용 문서 수준 사용자 지정에서 Windows Forms 컨트롤을 사용하여 텍스트 서식을 변경하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   디자인 타임에 문서 수준 프로젝트의 문서에 텍스트 및 컨트롤 추가  
  
-   옵션을 선택할 때 텍스트 서식 지정  
  
 결과를 전체 샘플로 보려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Word Controls 샘플을 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  이름이 My Word Formatting인 Word 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Word 문서가 열리고 **My Word Formatting** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## Word 문서에 텍스트 및 컨트롤 추가  
 이 연습에서는 Word 문서의 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 확인란 세 개와 텍스트를 추가합니다.  확인란은 사용자에게 텍스트 서식을 지정하기 위한 옵션을 제공합니다.  
  
#### 확인란 세 개를 추가하려면  
  
1.  Visual Studio 디자이너에 문서가 열려 있는지 확인합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 첫 번째 <xref:Microsoft.Office.Tools.Word.Controls.CheckBox> 컨트롤을 문서로 끌어 놓습니다.  
  
3.  **속성** 창에서 다음과 같이 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyBoldFont**|  
    |**텍스트**|굵게|  
  
4.  **Enter** 키를 눌러 삽입 지점을 첫 번째 확인란 아래로 옮깁니다.  
  
5.  문서의 `ApplyBoldFont` 확인란 아래에 두 번째 확인란을 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyItalicFont**|  
    |**텍스트**|기울임꼴|  
  
6.  **Enter** 키를 눌러 삽입 지점을 두 번째 확인란 아래로 옮깁니다.  
  
7.  문서의 `ApplyItalicFont` 확인란 아래에 세 번째 확인란을 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyUnderlineFont**|  
    |**텍스트**|Underline|  
  
#### 텍스트 및 Bookmark 컨트롤을 추가하려면  
  
1.  삽입 지점을 확인란 컨트롤 아래로 옮기고 다음 텍스트를 입력합니다.  
  
     이 텍스트의 서식을 변경하려면 확인란을 클릭하십시오.  
  
2.  **도구 상자**의 **Word 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서로 끌어 놓습니다.  
  
     **Bookmark 컨트롤 추가** 대화 상자가 나타납니다.  
  
3.  문서에 추가한 텍스트를 선택하고 **확인**을 클릭합니다.  
  
     **Bookmark1**이라는 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤이 문서에서 선택한 텍스트에 추가됩니다.  
  
4.  **속성** 창에서 **\(Name\)** 속성 값을 **fontText**로 변경합니다.  
  
 이제 확인란을 선택하거나 해제할 때 텍스트 서식을 지정하는 코드를 작성합니다.  
  
## 확인란을 선택 또는 해제할 때 텍스트 서식 지정  
 사용자가 서식 옵션을 선택하면 문서에 있는 텍스트의 서식이 변경됩니다.  
  
#### 확인란을 선택한 경우 서식을 변경하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 `ThisDocument`를 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  C\#의 경우 **ThisDocument** 클래스에 다음 상수를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#2)]  
  
3.  `applyBoldFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ThisDocument.vb#3)]  
  
4.  `applyItalicFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#4)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ThisDocument.vb#4)]  
  
5.  `applyUnderlineFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#5)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ThisDocument.vb#5)]  
  
6.  C\#의 경우 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트에 텍스트 상자에 대한 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#6)]  
  
## 응용 프로그램 테스트  
 이제 문서를 테스트하여 확인란을 선택하거나 해제할 때 텍스트의 서식이 올바르게 지정되는지 확인할 수 있습니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  확인란을 선택하거나 해제합니다.  
  
3.  텍스트의 서식이 올바르게 지정되는지 확인합니다.  
  
## 다음 단계  
 이 연습은 Word 문서에서 확인란을 사용하고 텍스트 서식을 프로그래밍 방식으로 변경하는 기본적인 방법을 보여 줍니다.  이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다.  자세한 내용은 [연습: 문서에서 단추를 사용하여 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md)을 참조하십시오.  
  
-   라디오 단추를 사용하여 차트 스타일을 선택합니다.  자세한 내용은 [연습: 문서에서 라디오 단추를 사용하여 차트 업데이트](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md)을 참조하십시오.  
  
## 참고 항목  
 [Word를 사용한 연습](../vsto/walkthroughs-using-word.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  