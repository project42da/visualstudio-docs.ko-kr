---
title: "연습: CheckBox 컨트롤을 사용 하 여 워크시트 서식 변경 | Microsoft Docs"
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
helpviewer_keywords:
- worksheets, changing formatting using managed controls
- worksheets, check box controls
- controls [Office development in Visual Studio], adding to worksheets
ms.assetid: 4be79613-50a0-428e-9816-aadbc098272a
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: e1729a7921f72df07439261cb054fe30770b24d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-changing-worksheet-formatting-using-checkbox-controls"></a>연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경
  이 연습에서는 Microsoft Office Excel 워크시트에서 확인란을 사용 하 여 서식을 변경 하는 기본적인 보여 줍니다. 만들고 프로젝트에 코드 추가 Visual Studio에서 Office 개발 도구를 사용 합니다. 결과 전체 샘플을 보려면 Excel 컨트롤 샘플을 참조 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   워크시트에 텍스트와 컨트롤을 추가 합니다.  
  
-   옵션을 선택할 때 텍스트의 서식을 지정 합니다.  
  
-   프로젝트를 테스트 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 이 단계에서는 Visual Studio를 사용 하 여 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **내 Excel 서식을**합니다. 다음 사항을 확인 **새 문서** 을 선택 합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **내 Excel 서식을** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-text-and-controls-to-the-worksheet"></a>워크시트에 텍스트 및 컨트롤 추가  
 이 연습에서는 해야 세 <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> 컨트롤 및 일부 텍스트에는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 제어 합니다.  
  
#### <a name="to-add-three-check-boxes"></a>확인란 세 개를 추가 하려면  
  
1.  통합 문서를 Visual Studio 디자이너에서 열려 있는지 확인 하십시오. `Sheet1` 열려 있습니다.  
  
2.  **공용 컨트롤** 탭은 **도구 상자**를 끌어 한 <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> 하거나 컨트롤을 셀 근처 **b 2** 에 **Sheet1**합니다.  
  
3.  **보기** 메뉴 선택 **속성** 창.  
  
4.  수 있도록 **Checkbox1** 의 개체 이름 목록 상자에 표시 되는 **속성** 창에서 다음 속성을 변경:  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**applyBoldFont**|  
    |**텍스트**|**굵게**|  
  
5.  두 번째 확인란을 위 또는 주변 셀에 끌어 놓고 **B4** 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**applyItalicFont**|  
    |**텍스트**|**기울임꼴**|  
  
6.  세 번째 확인란을 위 또는 주변 셀에 끌어 놓고 **B6** 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**applyUnderlineFont**|  
    |**텍스트**|**밑줄**|  
  
7.  CTRL 키를 누른 채 모든 세 확인란 컨트롤을 선택 합니다.  
  
8.  Excel의 서식 탭의 정렬 그룹에서 클릭 **맞춤**, 클릭 하 고 **왼쪽 맞춤**합니다.  
  
     세 가지 확인란 컨트롤이 선택한 첫 번째 컨트롤의 위치에서 왼쪽에 정렬 됩니다.  
  
     끌어 다음으로 <xref:Microsoft.Office.Tools.Excel.NamedRange> 워크시트에 컨트롤입니다.  
  
    > [!NOTE]  
    >  추가할 수도 있습니다는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 입력 하 여 컨트롤 **텍스트 글꼴** 에 **이름** 상자입니다.  
  
#### <a name="to-add-text-to-a-namedrange-control"></a>NamedRange 컨트롤에 텍스트를 추가 하려면  
  
1.  **Excel 컨트롤** 끌어서 도구 상자 탭은 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 셀 **b 9**합니다.  
  
2.  확인 **$B$ 9** 편집 가능한 텍스트 상자 및 해당 셀에 표시 **b 9** 을 선택 합니다. 그렇지 않은 경우 셀을 클릭 **b 9** 을 선택 합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  셀 **b 9** 라는 범위가 되 `NamedRange1`합니다.  
  
     워크시트에 있지만 `NamedRange1` 에 표시는 **이름 상자** (워크시트 바로 위 왼쪽) 셀 **b 9** 을 선택 합니다.  
  
5.  수 있도록 **NamedRange1** 의 개체 이름 목록 상자에 표시 되는 **속성** 창에서 다음 속성을 변경:  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**텍스트 글꼴**|  
    |**Value2**|**이 텍스트의 서식을 변경 하려면이 확인란을 클릭 합니다.**|  
  
 그런 다음 옵션을 선택할 때 텍스트의 서식을 지정 하려면 코드를 작성 합니다.  
  
## <a name="formatting-the-text-when-an-option-is-selected"></a>서식 지정 텍스트 때는 옵션을 선택 합니다.  
 이 섹션에서는 워크시트에 있는 텍스트의 형식이 변경 되는 사용자가 서식 옵션을 선택 되도록 코드를 작성 합니다.  
  
#### <a name="to-change-formatting-when-a-check-box-is-selected"></a>선택한 경우 확인란 서식을 변경 하려면  
  
1.  마우스 오른쪽 단추로 클릭 **Sheet1**, 클릭 하 고 **코드 보기** 바로 가기 메뉴.  
  
2.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 의 이벤트 처리기는 `applyBoldFont` 확인란:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#7)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#7)]  
  
3.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 의 이벤트 처리기는 `applyItalicFont` 확인란:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#8)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#8)]  
  
4.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 의 이벤트 처리기는 `applyUnderlineFont` 확인란:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#9)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#9)]  
  
5.  C#을 확인란에 대 한 이벤트 처리기를 추가 해야는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 아래와 같이 이벤트입니다. 이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#10)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 선택 하거나 확인란의 선택을 취소 때 텍스트의 서식이 올바르게 지정 되었는지 확인 하려면 통합 문서를 테스트할 수 있습니다.  
  
#### <a name="to-test-your-workbook"></a>통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  선택 하거나 확인란의 선택을 취소 합니다.  
  
3.  텍스트 올바르게 포맷 되어 있는지 확인 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 확인란을 사용 하 고 Excel 워크시트에서 텍스트 서식 지정의 기본 사항을 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)합니다.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다. 자세한 내용은 참조 [연습: 텍스트 상자에는 단추를 사용 하는 워크시트의 표시 텍스트](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  