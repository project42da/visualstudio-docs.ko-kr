---
title: "연습: 문서에서 라디오 단추를 사용하여 차트 업데이트 | Microsoft Docs"
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
  - "컨트롤[Visual Studio에서 Office 개발], 문서 업데이트"
  - "문서[Visual Studio에서 Office 개발], 컨트롤을 사용하여 업데이트"
ms.assetid: 56e6d1f2-65a4-41f0-aff5-f0cfd96d7185
caps.latest.revision: 60
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 59
---
# 연습: 문서에서 라디오 단추를 사용하여 차트 업데이트
  이 연습에서는 Microsoft Office Word의 문서 수준 사용자 지정에서 라디오 단추를 사용하여 문서에서 차트 스타일 선택 옵션을 사용자에게 제공하는 방법을 보여줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   디자인 타임에 문서 수준 프로젝트에서 문서에 차트를 추가합니다.  
  
-   라디오 단추를 사용자 컨트롤에 추가하여 그룹화합니다.  
  
-   옵션을 선택할 때 차트 스타일을 변경합니다.  
  
 결과를 완료된 샘플로 확인하려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Word 컨트롤 샘플을 참조하세요.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  이름이 **My Chart Options**인 Word 문서 프로젝트를 만듭니다.  이렇게 하려면 마법사에서 **새 문서 만들기**를 선택합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Word 문서가 열리고 **My Chart Options** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 문서에 차트 추가  
  
#### 차트를 추가하려면  
  
1.  Visual Studio 디자이너에서 호스팅되는 Word 문서의 리본 메뉴에서 **삽입** 탭을 클릭합니다.  
  
2.  **텍스트** 그룹에서 **개체 삽입** 드롭다운 단추를 클릭하고 **개체**를 클릭합니다.  
  
     **개체** 대화 상자가 열립니다.  
  
3.  **새로 만들기** 탭의 **개체 형식** 목록에서 **Microsoft Graph 차트**를 선택하고 **확인**을 클릭합니다.  
  
     문서의 삽입 지점에 차트가 추가되고 일부 기본 데이터가 포함된 **데이터시트** 창이 표시됩니다.  
  
4.  **데이터시트** 창을 닫아 차트의 기본값을 적용한 다음 문서 안을 클릭하여 포커스를 차트 외부로 이동합니다.  
  
5.  차트를 마우스 오른쪽 단추로 클릭한 다음 **개체 서식**을 클릭합니다.  
  
6.  **개체 서식** 대화 상자의 **레이아웃** 탭에서 **사각형**을 선택하고 **확인**을 클릭합니다.  
  
## 프로젝트에 사용자 컨트롤 추가  
 기본적으로 문서에서는 여러 라디오 단추를 함께 사용할 수 있습니다.  라디오 단추를 사용자 컨트롤에 추가한 다음 컨택을 제어하는 코드를 작성하여 해당 단추가 올바르게 작동하도록 지정할 수 있습니다.  
  
#### 사용자 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **My Chart Options** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 컨트롤**을 클릭하고 컨트롤의 이름을 **ChartOptions**로 지정한 후 **추가**를 클릭합니다.  
  
#### 사용자 컨트롤에 Windows Form 컨트롤을 추가하려면  
  
1.  사용자 컨트롤이 디자이너에 표시되지 않으면 **솔루션 탐색기**에서 **ChartOptions**를 두 번 클릭합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 첫 번째 **라디오 단추**를 사용자 컨트롤로 끌어 온 후 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**columnChart**|  
    |**Text**|세로 막대형 차트|  
  
3.  두 번째 **라디오 단추**를 사용자 컨트롤에 추가한 후 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**barChart**|  
    |**Text**|막대형 차트|  
  
4.  세 번째 **라디오 단추**를 사용자 컨트롤에 추가한 후 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**lineChart**|  
    |**Text**|꺾은선형 차트|  
  
5.  네 번째 **라디오 단추**를 사용자 컨트롤에 추가한 후 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**areaBlockChart**|  
    |**Text**|영역 블록 차트|  
  
## 참조 추가  
 문서의 사용자 컨트롤에서 차트에 액세스하려면 프로젝트에 Microsoft.Office.Interop.Graph 어셈블리에 대한 참조가 있어야 합니다.  
  
#### Microsoft.Office.Interop.Graph 어셈블리에 대한 참조를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
     **참조 추가** 대화 상자가 나타납니다.  
  
2.  **.NET** 탭에서 **Microsoft.Office.Interop.Graph**를 선택하고 **확인**을 클릭합니다.  어셈블리의 14.0.0.0 버전을 선택합니다.  
  
## 라디오 단추를 선택할 때 차트 스타일 변경  
 단추가 정상적으로 작동하도록 하려면 사용자 컨트롤에 대한 공용 이벤트를 만들고 선택 유형을 설정하는 속성을 추가한 다음 각 라디오 단추의 `CheckedChanged` 이벤트에 대해 프로시저를 만듭니다.  
  
#### 사용자 컨트롤에서 이벤트와 속성을 만들려면  
  
1.  **솔루션 탐색기**에서 사용자 컨트롤을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  
  
2.  `SelectionChanged` 이벤트와 `Selection` 속성을 만드는 코드를 `ChartOptions` 클래스에 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#9)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ChartOptions.vb#9)]  
  
#### 라디오 단추의 CheckedChange 이벤트를 처리하려면  
  
1.  `areaBlockChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정한 다음 이벤트를 발생시킵니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#10)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ChartOptions.vb#10)]  
  
2.  `barChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#11)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ChartOptions.vb#11)]  
  
3.  `columnChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#12)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ChartOptions.vb#12)]  
  
4.  `lineChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#13)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ChartOptions.vb#13)]  
  
5.  C\#에서는 라디오 단추에 대해 이벤트 처리기를 추가해야 합니다.  `ChartOptions` 생성자의 `InitializeComponent` 호출 아래에 코드를 추가할 수 있습니다.  이벤트 처리기 만들기에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하세요.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ChartOptions.cs#14)]  
  
## 문서에 사용자 컨트롤 추가  
 솔루션을 빌드하면 새 사용자 컨트롤이 **도구 상자**에 자동으로 추가됩니다.  그러면 컨트롤을 **도구 상자**에서 문서로 끌어 올 수 있습니다.  
  
#### 문서에 사용자 정의 컨트롤을 추가하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **ChartOptions** 사용자 컨트롤이 **도구 상자**에 추가됩니다.  
  
2.  **솔루션 탐색기**에서 **ThisDocument.vb** 또는 **ThisDocument.cs**를 마우스 오른쪽 단추로 클릭하고 **디자이너 보기**를 클릭합니다.  
  
3.  **도구 상자**에서 문서로 `ChartOptions` 컨트롤을 끌어 옵니다.  
  
     **속성** 창에서 방금 문서에 추가한 컨트롤의 이름을 `ChartOptions1`로 설정합니다.  
  
## 차트 종류 변경  
 사용자 컨트롤에서 선택하는 옵션에 따라 차트 종류를 변경하는 이벤트 처리기를 만듭니다.  
  
#### 문서에 표시되는 차트의 종류를 변경하려면  
  
1.  `ThisDocument` 클래스에 다음 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#15)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/VB/ThisDocument.vb#15)]  
  
2.  C\#에서는 사용자 컨트롤에 대한 이벤트 처리기를 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트에 추가해야 합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsWord/CS/ThisDocument.cs#16)]  
  
## 응용 프로그램 테스트  
 이제 문서를 테스트하여 라디오 단추를 선택할 때 차트 스타일이 올바르게 업데이트되는지 확인할 수 있습니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  여러 라디오 단추를 선택합니다.  
  
3.  선택 항목과 일치하도록 차트 스타일이 변경되는지 확인합니다.  
  
## 다음 단계  
 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다.  자세한 내용은 [연습: 문서에서 단추를 사용하여 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md)을 참조하십시오.  
  
-   콤보 상자에서 스타일을 선택하여 서식을 변경합니다.  자세한 내용은 [연습: CheckBox 컨트롤을 사용하여 문서 서식 변경](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)을 참조하십시오.  
  
## 참고 항목  
 [Word를 사용한 연습](../vsto/walkthroughs-using-word.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  