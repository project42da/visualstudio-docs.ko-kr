---
title: "연습: NamedRange 컨트롤의 이벤트 프로그래밍 | Microsoft Docs"
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
- ranges, programming against events
- worksheets, changing cell values
- NamedRange control, events
- worksheets, events
- worksheets, automating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a06e8aa544cdaff2e75d8af942f8aea68e7bc960
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-programming-against-events-of-a-namedrange-control"></a>연습: NamedRange 컨트롤의 이벤트 프로그래밍
  이 연습에서는 추가 하는 방법을 보여 줍니다.는 <xref:Microsoft.Office.Tools.Excel.NamedRange> Microsoft Office Excel 워크시트 및 Visual Studio에서 Office 개발 도구를 사용 하 여 사용 하 여 해당 이벤트에 대해 프로그래밍 하는 컨트롤입니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   추가 <xref:Microsoft.Office.Tools.Excel.NamedRange> 워크시트에 컨트롤입니다.  
  
-   에 대 한 프로그램 <xref:Microsoft.Office.Tools.Excel.NamedRange> 이벤트를 제어 합니다.  
  
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
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **명명 된 범위 내 이벤트**합니다. 다음 사항을 확인 **새 문서** 을 선택 합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **명명 된 범위 내 이벤트** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-text-and-named-ranges-to-the-worksheet"></a>텍스트를 추가 하 고 명명 된 범위는 워크시트에  
 호스트 컨트롤은 Office 개체를 확장 하기 때문에 추가할 수 있습니다는 네이티브 개체를 추가 하는 동일한 방식으로 문서입니다. 예를 들어 Excel을 추가할 수 있습니다 <xref:Microsoft.Office.Tools.Excel.NamedRange> 열어 워크시트에 컨트롤의 **삽입** 가리키는 메뉴 **이름**, 선택 하 고 **정의**합니다. 추가할 수도 있습니다는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤에서 끌어서는 **도구 상자** 워크시트입니다.  
  
 이 단계에서 사용 하 여 워크시트에 두 개의 명명 된 범위 컨트롤을 추가 합니다는 **도구 상자**, 워크시트에 텍스트를 추가 합니다.  
  
#### <a name="to-add-a-range-to-your-worksheet"></a>범위를 워크시트에 추가 하려면  
  
1.  되어 있는지 확인는 **내 명명 된 범위 Events.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 `Sheet1` 표시 합니다.  
  
2.  **Excel 컨트롤** 끌어서 도구 상자 탭은 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 셀 **A1** 에서 `Sheet1`합니다.  
  
     **NamedRange 컨트롤 추가** 대화 상자가 나타납니다.  
  
3.  확인 **$A$ 1** 편집 가능한 텍스트 상자 및 해당 셀에 표시 **A1** 을 선택 합니다. 그렇지 않은 경우 셀을 클릭 **A1** 을 선택 합니다.  
  
4.  **확인**을 클릭합니다.  
  
     셀 **A1** 라는 범위가 되 `namedRange1`합니다. 워크시트에 있지만 `namedRange1` 에 표시는 **이름** (왼쪽에 워크시트 바로 위에 있음) 상자 셀 **A1** 을 선택 합니다.  
  
5.  다른 항목 추가 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 셀 **B3**합니다.  
  
6.  확인 **$B$ 3** 편집 가능한 텍스트 상자 및 해당 셀에 표시 **B3** 을 선택 합니다. 그렇지 않은 경우 셀을 클릭 **B3** 을 선택 합니다.  
  
7.  **확인**을 클릭합니다.  
  
     셀 **B3** 라는 범위가 되 `namedRange2`합니다.  
  
#### <a name="to-add-text-to-your-worksheet"></a>워크시트에 텍스트를 추가 하려면  
  
1.  셀에 **A1**를 다음 텍스트를 입력 합니다.  
  
     **이것이 NamedRange 컨트롤의 예입니다.**  
  
2.  셀에 **A3** (왼쪽의 `namedRange2`)를 다음 텍스트를 입력 합니다.  
  
     **이벤트:**  
  
 다음 섹션에 텍스트를 삽입 하는 코드를 작성 합니다 `namedRange2` 의 속성을 수정 하 고는 `namedRange2` 컨트롤에 대 한 응답에는 <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>, <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>, 및 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 의 이벤트 `namedRange1`합니다.  
  
## <a name="adding-code-to-respond-to-the-beforedoubleclick-event"></a>BeforeDoubleClick 이벤트에 응답 하는 코드를 추가 합니다.  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-beforedoubleclick-event"></a>NamedRange2 BeforeDoubleClick 이벤트를 기준으로 텍스트를 삽입 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Sheet1.vb** 또는 **Sheet1.cs** 선택 **코드 보기**합니다.  
  
2.  코드를 추가 하므로 `namedRange1_BeforeDoubleClick` 이벤트 처리기는 다음과 같습니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#24)]  
  
3.  C#에서 추가 해야에 표시 된 대로 명명된 된 범위에 대 한 이벤트 처리기는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 아래의 이벤트입니다. 이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#25](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#25)]  
  
## <a name="adding-code-to-respond-to-the-change-event"></a>변경 이벤트에 응답 하는 코드를 추가 합니다.  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-change-event"></a>텍스트 변경 이벤트에 따라 namedRange2를 삽입 하려면  
  
1.  코드를 추가 하므로 `NamedRange1_Change` 이벤트 처리기는 다음과 같습니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#26)]  
  
    > [!NOTE]  
    >  Excel 범위에 있는 셀을 두 번 클릭으로 편집 모드로 전환 하기 때문에 한 <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> 이벤트 텍스트에 변경 사항이 발생 한 경우에 선택 범위를 벗어난 이동할 때 발생 합니다.  
  
## <a name="adding-code-to-respond-to-the-selectionchange-event"></a>SelectionChange 이벤트에 응답 하는 코드를 추가 합니다.  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-selectionchange-event"></a>SelectionChange 이벤트에 따라 namedRange2에 텍스트를 삽입 하려면  
  
1.  코드를 추가 하므로 **NamedRange1_SelectionChange** 이벤트 처리기는 다음과 같습니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#27)]  
  
    > [!NOTE]  
    >  에 범위로 이동 하 고 선택 영역 Excel 범위에 있는 셀을 두 번 클릭 하면 때문에 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 이벤트가 발생 하기 전에 <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> 이벤트가 발생 합니다.  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이벤트를 설명 하는 해당 텍스트를 확인 하려면 통합 문서를 테스트할 수 이제는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 는 이벤트가 발생 하는 경우 다른 명명 된 범위에 컨트롤 삽입 됩니다.  
  
#### <a name="to-test-your-document"></a>문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  에 커서를 놓고 `namedRange1`, 되어 있는지 확인 하 고 텍스트에 대 한는 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 이벤트 삽입 되 고 워크시트에 주석을 삽입 합니다.  
  
3.  안쪽을 두 번 클릭 `namedRange1`, 되어 있는지 확인 하 고 텍스트에 대 한 <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> 이벤트에서 빨간색 기울임꼴 텍스트로 삽입 됩니다 `namedRange2`합니다.  
  
4.  외부의 클릭 `namedRange1` 편집 모드를 변경 하지 않습니다는 텍스트에도 변경 이벤트 발생을 끝낼 때 있는지 확인 합니다.  
  
5.  내에서 텍스트를 변경 `namedRange1`합니다.  
  
6.  외부의 클릭 `namedRange1`, 되어 있는지 확인 하 고 텍스트에 대 한 <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> 이벤트 파란색 텍스트를 함께 삽입 됩니다 `namedRange2`합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는의 이벤트에 대 한 프로그래밍의 기본 사항을 보여 줍니다.는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 제어 합니다. 다음으로 수행할 수 있는 태스크는 다음과 같습니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: NamedRange 컨트롤 크기 조정](../vsto/how-to-resize-namedrange-controls.md)   
 [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)  
  
  