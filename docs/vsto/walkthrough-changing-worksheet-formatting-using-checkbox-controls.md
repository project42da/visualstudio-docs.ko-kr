---
title: "연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경"
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
  - "컨트롤[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "워크시트, 관리되는 컨트롤을 사용하여 서식 변경"
  - "워크시트, check box 컨트롤"
ms.assetid: 4be79613-50a0-428e-9816-aadbc098272a
caps.latest.revision: 70
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 69
---
# 연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경
  이 연습에서는 Microsoft Office Excel 워크시트에서 확인란을 사용하여 서식을 변경하는 기본 방법을 보여 줍니다.  Visual Studio의 Office 개발 도구를 사용하여 코드를 만들어 프로젝트에 추가합니다.  결과를 완성된 샘플로 보려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Excel 컨트롤 샘플을 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습을 통해 다음과 같은 작업 방법을 배웁니다.  
  
-   워크시트에 텍스트 및 컨트롤 추가  
  
-   옵션을 선택할 때 텍스트 서식 지정  
  
-   프로젝트 테스트  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## 프로젝트 만들기  
 이 단계에서는 Visual Studio를 사용하여 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  My Excel Formatting이라는 Excel 통합 문서 프로젝트를 만듭니다.  **새 문서 만들기**가 선택되어 있는지 확인합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 **My Excel Formatting** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 워크시트에 텍스트 및 컨트롤 추가  
 이 연습에서는 세 <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> 컨트롤과 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 일부 텍스트가 필요합니다.  
  
#### 확인란 세 개를 추가하려면  
  
1.  Visual Studio 디자이너에 통합 문서가 열려 있고 `Sheet1`이 표시되어 있는지 확인합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> 컨트롤을 **Sheet1**의 **B2** 셀이나 이 셀 근처에 끌어 놓습니다.  
  
3.  **보기** 메뉴에서 **속성** 창을 선택합니다.  
  
4.  **속성** 창의 개체 이름 목록 상자에 **Checkbox1**이 표시되어 있는지 확인하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyBoldFont**|  
    |**텍스트**|굵게|  
  
5.  두 번째 확인란을 **B4** 셀이나 이 셀 근처에 끌어 놓고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyItalicFont**|  
    |**텍스트**|기울임꼴|  
  
6.  세 번째 확인란을 **B6** 셀이나 이 셀 근처에 끌어 놓고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**applyUnderlineFont**|  
    |**텍스트**|Underline|  
  
7.  Ctrl 키를 누른 채로 확인란 컨트롤 세 개를 모두 선택합니다.  
  
8.  Excel에서 서식 탭의 정렬 그룹에서 클릭  **맞춤**를 클릭 하 고 다음을 클릭  **왼쪽 맞춤**.  
  
     세 개의 확인란 컨트롤에서 선택한 첫 번째 컨트롤의 위치를 왼쪽에 맞춥니다.  
  
     이제 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 워크시트에 끌어 놓습니다.  
  
    > [!NOTE]  
    >  **이름** 상자에 **textFont**를 입력하여 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 추가할 수도 있습니다.  
  
#### NamedRange 컨트롤에 텍스트를 추가하려면  
  
1.  도구 상자의 **Excel 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 **B9** 셀로 끌어 놓습니다.  
  
2.  편집할 수 있는 텍스트 상자에 **$B$9**가 표시되어 있고 **B9** 셀이 선택되어 있는지 확인합니다.  **B9** 셀이 선택되어 있지 않으면 이 셀을 클릭하여 선택합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  **B9** 셀이 `NamedRange1`이라는 범위가 됩니다.  
  
     워크시트에 시각적으로 표시되지는 않지만 **B9** 셀을 선택하면 워크시트의 왼쪽 바로 위에 있는 **이름 상자**에 `NamedRange1`이 나타납니다.  
  
5.  **속성** 창의 개체 이름 목록 상자에 **NamedRange1**이 표시되어 있는지 확인하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**textFont**|  
    |**Value2**|이 텍스트의 서식을 변경하려면 확인란을 클릭하십시오.|  
  
 이제 옵션을 선택할 때 텍스트의 서식을 지정하기 위한 코드를 작성합니다.  
  
## 옵션을 선택할 때 텍스트 서식 지정  
 이 단원에서는 사용자가 서식 지정 옵션을 선택할 때 워크시트의 텍스트 서식이 변경되도록 코드를 작성합니다.  
  
#### 확인란을 선택한 경우 서식을 변경하려면  
  
1.  마우스 오른쪽 단추로 **Sheet1**을 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `applyBoldFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#7)]  
  
3.  `applyItalicFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#8)]  
  
4.  `applyUnderlineFont` 확인란의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#9)]  
  
5.  C\#의 경우 아래와 같이 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트에 확인란에 대한 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#10)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 확인란을 선택하거나 해제할 때 텍스트의 서식이 올바르게 지정되는지 확인할 수 있습니다.  
  
#### 통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  확인란을 선택하거나 해제합니다.  
  
3.  텍스트의 서식이 올바르게 지정되는지 확인합니다.  
  
## 다음 단계  
 이 연습에서는 Excel 워크시트에서 확인란을 사용하고 텍스트의 서식을 지정하는 기본적인 방법을 보여 줍니다.  이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)을 참조하십시오.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다.  자세한 내용은 [연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)을 참조하십시오.  
  
## 참고 항목  
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  