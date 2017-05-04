---
title: "연습: 문서에서 단추를 사용하여 텍스트 상자에 텍스트 표시 | Microsoft Docs"
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
  - "텍스트 상자, 문서에 텍스트 표시"
ms.assetid: 04c54ed7-9f00-4068-aaec-1f3200110116
caps.latest.revision: 60
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 59
---
# 연습: 문서에서 단추를 사용하여 텍스트 상자에 텍스트 표시
  이 연습에서는 Microsoft Office Word에 대한 문서 수준 사용자 지정에서 단추 및 텍스트 상자를 사용하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   디자인 타임에 문서 수준 프로젝트의 Word 문서에 컨트롤 추가  
  
-   단추를 클릭할 때 텍스트 상자 채우기  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  이름이 My Word Button인 Word 문서 프로젝트를 만듭니다.  이렇게 하려면 마법사에서 **새 문서 만들기**를 선택합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
     Visual Studio의 디자이너에서 새 Word 문서가 열리고 **My Word Button** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## Word 문서에 컨트롤 추가  
 Word 문서의 사용자 인터페이스 컨트롤은 단추와 텍스트 상자로 구성됩니다.  
  
#### 단추 및 텍스트 상자를 추가하려면  
  
1.  Visual Studio 디자이너에서 문서가 열려 있는지 확인합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Word.Controls.TextBox> 컨트롤을 문서로 끌어 놓습니다.  
  
    > [!NOTE]  
    >  Word에서는 기본적으로 컨트롤이 텍스트와 인라인으로 놓입니다.  Word **옵션** 대화 상자의 **편집** 탭에서 기본값을 변경하여 컨트롤 및 도형 개체가 삽입되는 방식을 수정할 수 있습니다.  
  
3.  **보기** 메뉴에서 **속성 창**을 클릭합니다.  
  
4.  **속성** 창 드롭다운 상자에서 **TextBox1**을 찾아 텍스트 상자의 **이름** 속성을 **displayText**로 변경합니다.  
  
5.  **단추** 컨트롤을 문서로 끌고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**insertText**|  
    |**텍스트**|텍스트 삽입|  
  
 이제 단추를 클릭할 때 실행되는 코드를 작성할 수 있습니다.  
  
## 단추를 클릭할 때 텍스트 상자 채우기  
 사용자가 단추를 클릭할 때마다 **Hello World\!**가 텍스트 상자에 추가됩니다.  
  
#### 단추를 클릭할 때 텍스트 상자에 쓰려면  
  
1.  **솔루션 탐색기**에서 **ThisDocument**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ThisDocument.vb#7)]  
  
3.  C\#에서는 단추에 대한 이벤트 처리기를 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트에 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하세요.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#8)]  
  
## 응용 프로그램 테스트  
 이제 문서를 테스트하여 단추를 클릭할 때 **Hello World\!** 메시지가 텍스트 상자에 표시되는지 확인할 수 있습니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  단추를 클릭합니다.  
  
3.  **Hello World\!**가 텍스트 상자에 표시되는지 확인합니다.  
  
## 다음 단계  
 이 연습에서는 Word 문서에서 단추 및 텍스트 상자를 사용하는 기본 사항을 보여 줍니다.  다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   콤보 상자를 사용하여 서식 변경.  자세한 내용은 [연습: CheckBox 컨트롤을 사용하여 문서 서식 변경](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)을 참조하세요.  
  
-   라디오 단추를 사용하여 차트 스타일 선택.  자세한 내용은 [연습: 문서에서 라디오 단추를 사용하여 차트 업데이트](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md)를 참조하세요.  
  
## 참고 항목  
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Word를 사용한 연습](../vsto/walkthroughs-using-word.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  