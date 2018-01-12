---
title: "연습: 라디오 단추를 사용 하 여 워크시트에 차트를 업데이트 | Microsoft Docs"
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
- worksheets, updating using managed controls
- controls [Office development in Visual Studio], updating worksheets
- worksheets, using radio buttons
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 36a83dc849260f9d58595e2f52bb422a1854b5ec
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons"></a>연습: 워크시트에서 라디오 단추를 사용하여 차트 업데이트
  이 연습에서는 Microsoft Office Excel 워크시트에서 라디오 단추를 사용 하 여 신속 하 게 옵션 간에 전환 하는 방법을 사용자에 게 부여의 기본 사항을 보여 줍니다. 이 경우 옵션은 차트의 스타일을 변경합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 결과 전체 샘플을 보려면 Excel 컨트롤 샘플을 참조 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   라디오 단추 그룹을 워크시트에 추가 합니다.  
  
-   옵션을 선택할 때 차트 스타일을 변경합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## <a name="adding-a-chart-to-a-worksheet"></a>워크시트에 차트 추가  
 기존 통합 문서를 사용자 지정 하는 Excel 통합 문서 프로젝트를 만들 수 있습니다. 이 연습에서는 통합 문서에 차트를 추가 하 고이 통합 문서를 사용 하 여 새 Excel 솔루션에. 이 연습에서는 데이터 원본이 이라는 워크시트 **차트에 대 한 데이터**합니다.  
  
#### <a name="to-add-the-data"></a>데이터를 추가 하려면  
  
1.  Microsoft Excel을 엽니다.  
  
2.  마우스 오른쪽 단추로 클릭는 **Sheet3** 탭을 클릭 한 다음 **이름 바꾸기** 바로 가기 메뉴.  
  
3.  시트 이름 바꾸기 **차트에 대 한 데이터**합니다.  
  
4.  다음 데이터를 추가 **차트에 대 한 데이터** A4 셀 되 고 왼쪽 위 모서리 고 E8 오른쪽 아래 모서리 합니다.  
  
    ||Q1|Q 2|Q 3|Q 4|  
    |-|--------|--------|--------|--------|  
    |서 부|500|550|550|600|  
    |동부|600|625|675|700|  
    |북부|450|470|490|510|  
    |남부|800|750|775|790|  
  
 다음으로 데이터를 표시 하는 첫 번째 워크시트에 차트를 추가 합니다.  
  
#### <a name="to-add-a-chart-in-excel"></a>Excel에서 차트를 추가 하려면  
  
1.  에 **삽입** 탭에 **차트** 그룹에서 클릭 **열**, 클릭 하 고 **모든 차트 종류**합니다.  
  
2.  에 **차트 삽입** 대화 상자를 클릭 **확인**합니다.  
  
3.  에 **디자인** 탭에 **데이터** 그룹에서 클릭 **데이터 선택**합니다.  
  
4.  에 **데이터 원본 선택** 대화 상자에서를 클릭 하 고 **Chartdata 범위** 상자 하 고 기본 선택 값을 지웁니다.  
  
5.  에 **차트에 대 한 데이터** 시트 스타일을 셀의 오른쪽 아래에 e8 왼쪽된 위 모서리에 A4를 포함 하는 숫자가 포함 된 블록을 선택 합니다.  
  
6.  에 **데이터 원본 선택** 대화 상자를 클릭 **확인**합니다.  
  
7.  오른쪽 위 모서리 셀과 정렬 되도록 차트를 다시 배치 **E2**합니다.  
  
8.  C 드라이브에 파일을 저장 하 고 이름을 **ExcelChart.xlsx**합니다.  
  
9. Excel을 종료합니다.  
  
## <a name="creating-a-new-project"></a>새 프로젝트 만들기  
 이 단계에 따라 Excel 통합 문서 프로젝트를 만듭니다는 **ExcelChart** 통합 문서.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **내 Excel 차트**합니다. 마법사에서 선택 **기존 문서 복사**합니다.  
  
     자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
2.  클릭는 **찾아보기** 이 연습의 앞부분에서 만든 통합 문서를 buttonand 찾습니다.  
  
3.  **확인**을 클릭합니다.  
  
     Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **내 Excel 차트** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="setting-properties-of-the-chart"></a>차트의 속성 설정  
 기존 통합 문서를 사용 하는 새 Excel 통합 문서 프로젝트를 만들 때 모든 명명 된 범위, 목록 개체 및 통합 문서에 차트 호스트 컨트롤 자동으로 만들어집니다. 이름을 변경할 수 있습니다는 <xref:Microsoft.Office.Tools.Excel.Chart> 사용 하 여 컨트롤의 **속성** 창.  
  
#### <a name="to-change-the-name-of-the-chart-control"></a>차트 컨트롤의 이름을 변경 하려면  
  
1.  선택 된 <xref:Microsoft.Office.Tools.Excel.Chart> 디자이너에서 제어 하 고에서 다음 속성을 변경할는 **속성** 창.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**dataChart**|  
    |**HasLegend**|**false**|  
  
## <a name="adding-controls"></a>컨트롤 추가  
 이 워크시트는 신속 하 게 차트 스타일을 변경 하는 방법을 사용자에 게 라디오 단추를 사용 합니다. 그러나 라디오 단추 단독 잠금 일 필요가-그룹의 다른 단추 한 단추를 선택 하 고, 동시에 선택할 수 있습니다. 워크시트에 여러 라디오 단추를 추가할 때 기본적으로이 문제를 발생 하지 않습니다.  
  
 이 동작은 사용자 정의 컨트롤의 라디오 단추 그룹화 하는 것을 추가 하는 한 가지 방법은 사용자 정의 컨트롤 뒤에 코드를 작성 하 고 워크시트에 사용자 정의 컨트롤을 추가 합니다.  
  
#### <a name="to-add-a-user-control"></a>사용자 컨트롤을 추가하려면  
  
1.  선택 된 **내 Excel 차트** 프로젝트에서 **솔루션 탐색기**합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  에 **새 항목 추가** 대화 상자를 클릭 **사용자 정의 컨트롤**, 컨트롤의 이름을 지정 **ChartOptions** 클릭 **추가**합니다.  
  
#### <a name="to-add-radio-buttons-to-the-user-control"></a>사용자 컨트롤에 라디오 단추를 추가 하려면  
  
1.  사용자 컨트롤이 디자이너에 표시 되지 않으면, 두 번 클릭 **ChartOptions** 에 **솔루션 탐색기**합니다.  
  
2.  **공용 컨트롤** 탭은 **도구 상자**를 끌어 한 **라디오 단추** 사용자 정의 컨트롤을 제어 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**columnChart**|  
    |**텍스트**|**세로 막대형 차트**|  
  
3.  사용자 정의 컨트롤을 두 번째 라디오 단추를 추가 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**barChart**|  
    |**텍스트**|**가로 막대형 차트**|  
  
4.  사용자 정의 컨트롤에 세 번째 라디오 단추를 추가 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**lineChart**|  
    |**텍스트**|**꺾은선형 차트**|  
  
5.  사용자 정의 컨트롤에 네 번째 라디오 단추를 추가 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**areaBlockChart**|  
    |**텍스트**|**영역 블록 차트**|  
  
 다음으로, 라디오 단추를 클릭 하면 차트를 업데이트 하는 코드를 작성 합니다.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>변경 차트 스타일 때 정도 라디오 버튼을 선택 합니다.  
 이제 차트 스타일을 변경 하는 코드를 추가할 수 있습니다. 이 수행 하려면 사용자 정의 컨트롤에는 공용 이벤트를 만들고, 선택 유형을 설정 하는 속성을 추가 및에 대 한 이벤트 처리기를 만들고는 `CheckedChanged` 라디오 단추의 각 이벤트에 있습니다.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>사용자 컨트롤에서 이벤트와 속성을 만들려면  
  
1.  **솔루션 탐색기**사용자 정의 컨트롤을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **코드 보기**합니다.  
  
2.  코드를 추가 하는 `ChartOptions` 만들 클래스는 `SelectionChanged` 이벤트 및 `Selection` 속성입니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#13)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#13)]  
  
#### <a name="to-handle-the-checkedchanged-event-of-the-radio-buttons"></a>라디오 단추의 CheckedChanged 이벤트를 처리 하려면  
  
1.  `CheckedChanged` 라디오 단추의 `areaBlockChart` 이벤트 처리기에서 차트 종류를 설정한 다음 이벤트를 발생시킵니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#14)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#14)]  
  
2.  `CheckedChanged` 라디오 단추의 `barChart` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#15)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#15)]  
  
3.  `CheckedChanged` 라디오 단추의 `columnChart` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#16)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#16)]  
  
4.  `CheckedChanged` 라디오 단추의 `lineChart` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#17)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#17)]  
  
5.  C#에서는 라디오 단추에 대해 이벤트 처리기를 추가해야 합니다. `ChartOptions` 생성자의 `InitializeComponent` 호출 아래에 코드를 추가할 수 있습니다. 이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#18)]  
  
## <a name="adding-the-user-control-to-the-worksheet"></a>사용자 정의 컨트롤을 워크시트에 추가  
 새 사용자 정의 컨트롤에 자동으로 추가 되는 솔루션을 빌드할 때는 **도구 상자**합니다. 컨트롤을 끌어 놓을 수 있습니다는 **도구 상자** 을 워크시트에 있습니다.  
  
#### <a name="to-add-the-user-control-your-worksheet"></a>워크시트에 사용자 정의 컨트롤을 추가 하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **ChartOptions** 사용자 정의 컨트롤에 추가 되는 **도구 상자**합니다.  
  
2.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Sheet1.vb** 또는 **Sheet1.cs**, 클릭 하 고 **뷰 디자이너**합니다.  
  
3.  끌어서는 **ChartOptions** 에서 제어는 **도구 상자** 워크시트에 있습니다.  
  
     라는 새 컨트롤 `my_Excel_Chart_ChartOptions1` 프로젝트에 추가 합니다.  
  
4.  컨트롤의 이름을 변경 **ChartOptions1**합니다.  
  
## <a name="changing-the-chart-type"></a>차트 종류 변경  
 차트 종류를 변경 하려면 사용자 정의 컨트롤에서 선택한 옵션에 따라 스타일을 설정 하는 이벤트 처리기를 만듭니다.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-worksheet"></a>워크시트에 표시 되는 차트 종류를 변경 하려면  
  
1.  `Sheet1` 클래스에 다음 이벤트 처리기를 추가합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#19)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#19)]  
  
2.  C#에서는 사용자 정의 컨트롤에 대 한 이벤트 처리기를 추가 해야 합니다는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 아래와 같이 이벤트입니다. 이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#20)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 라디오 단추를 선택 하면 차트의 올바르게 스타일을 확인 하려면 통합 문서를 테스트할 수 있습니다.  
  
#### <a name="to-test-your-workbook"></a>통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  여러 라디오 단추를 선택합니다.  
  
3.  선택 항목과 일치하도록 차트 스타일이 변경되는지 확인합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 워크시트에서 라디오 단추와 차트 스타일을 사용 하는 기본적인 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)합니다.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다. 자세한 내용은 참조 [연습: 텍스트 상자에는 단추를 사용 하는 워크시트의 표시 텍스트](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)합니다.  
  
-   워크시트에서 확인란을 사용 하 여 서식을 변경 합니다. 자세한 내용은 참조 [연습: 변경 워크시트 서식을 사용 하 여 CheckBox 컨트롤](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)  
  
  