---
title: "연습: 워크시트에서 라디오 단추를 사용하여 차트 업데이트 | Microsoft Docs"
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
  - "컨트롤[Visual Studio에서 Office 개발], 워크시트 업데이트"
  - "워크시트, 관리되는 컨트롤을 사용하여 업데이트"
  - "워크시트, 라디오 단추 사용"
ms.assetid: cacc43a3-6d95-4a47-b943-3457d97a16f8
caps.latest.revision: 58
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 57
---
# 연습: 워크시트에서 라디오 단추를 사용하여 차트 업데이트
  이 연습에서는 Microsoft Office Excel 워크시트에서 라디오 단추를 사용하여 사용자가 옵션을 빠르게 전환할 수 있도록 하는 기본적인 방법을 보여 줍니다.  이 연습의 경우에는 차트 스타일을 변경하는 옵션을 대상으로 합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 결과를 완성된 샘플로 보려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Excel 컨트롤 샘플을 참조하십시오.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   워크시트에 라디오 단추 그룹 추가  
  
-   옵션을 선택할 때 차트 스타일 변경  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## 워크시트에 차트 추가  
 기존 통합 문서를 사용자 지정하는 Excel 통합 문서 프로젝트를 만들 수 있습니다.  이 연습에서는 통합 문서에 차트를 추가한 다음 이 통합 문서를 새 Excel 솔루션에서 사용합니다.  이 연습에서 데이터 소스는 **Data for Chart**라는 이름의 워크시트입니다.  
  
#### 데이터를 추가하려면  
  
1.  Microsoft Excel을 엽니다.  
  
2.  **Sheet3** 탭을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 클릭합니다.  
  
3.  시트의 이름을 Data for Chart로 변경합니다.  
  
4.  A4 셀을 왼쪽 위 모퉁이로 하고 E8 셀을 오른쪽 아래 모퉁이로 하여 **Data for Chart**에 다음 데이터를 추가합니다.  
  
    ||Q1|Q2|Q3|Q4|  
    |-|--------|--------|--------|--------|  
    |West|500|550|550|600|  
    |East|600|625|675|700|  
    |North|450|470|490|510|  
    |South|800|750|775|790|  
  
 그런 다음 첫 번째 워크시트에 차트를 추가하여 데이터를 표시합니다.  
  
#### Excel에서 차트를 추가하려면  
  
1.  **삽입** 탭의 **차트** 그룹에서 **열**을 클릭한 다음 **모든 차트 종류**를 클릭합니다.  
  
2.  **차트 삽입** 대화 상자에서 **확인**을 클릭합니다.  
  
3.  **디자인** 탭의 **데이터** 그룹에서 **데이터 선택**을 클릭합니다.  
  
4.  **데이터 원본 선택** 대화 상자에서 **차트데이터 범위** 상자를 클릭하고 기본 선택 값을 지웁니다.  
  
5.  **Data for Chart** 시트에서 왼쪽 위 모퉁이의 A4 셀부터 오른쪽 아래 모퉁이의 E8 셀까지 포함되도록 숫자가 들어 있는 셀 블록을 선택합니다.  
  
6.  **데이터 원본 선택** 대화 상자에서 **확인**을 클릭합니다.  
  
7.  차트의 오른쪽 위 모퉁이가 **E2** 셀과 정렬되도록 차트를 다시 배치합니다.  
  
8.  C 드라이브에 파일을 저장 하 고 이름을  **ExcelChart.xlsx**.  
  
9. Excel을 종료합니다.  
  
## 새 프로젝트 만들기  
 이 단계에서는 **ExcelChart** 통합 문서를 기반으로 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  **My Excel Chart**라는 Excel 통합 문서 프로젝트를 만듭니다.  마법사에서 **기존 문서 복사**를 선택합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
2.  클릭 하 여  **찾아보기**  단추및 이전에이 연습에서 만든 통합 문서를 찾습니다.  
  
3.  **확인**을 클릭합니다.  
  
     Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 **My Excel Chart** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 차트의 속성 설정  
 기존 통합 문서를 사용하는 새 Excel 통합 문서 프로젝트를 만들면 통합 문서 내에 있는 모든 명명된 범위, 목록 개체 및 차트에 대해 호스트 컨트롤이 자동으로 만들어집니다.  **속성** 창을 사용하여 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤의 이름을 변경할 수 있습니다.  
  
#### 차트 컨트롤의 이름을 변경하려면  
  
1.  디자이너에서 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 선택하고 **속성** 창에서 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**dataChart**|  
    |**HasLegend**|**false**|  
  
## 컨트롤 추가  
 이 워크시트에서는 라디오 단추를 사용하여 사용자가 차트 스타일을 빠르게 변경할 수 있도록 합니다.  그러나 라디오 단추는 한 번에 하나만 선택해야 합니다. 즉, 한 단추가 선택된 상태에서 그룹의 다른 단추를 동시에 선택할 수 없습니다.  워크시트에 여러 개의 라디오 단추를 추가할 때 기본적으로는 이 동작이 적용되지 않습니다.  
  
 이 동작을 추가하는 한 가지 방법은 라디오 단추를 사용자 정의 컨트롤에 그룹화하고 해당 사용자 정의 컨트롤의 숨김 코드를 작성한 다음 이 사용자 정의 컨트롤을 워크시트에 추가하는 것입니다.  
  
#### 사용자 정의 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **My Excel Chart** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 정의 컨트롤**을 클릭하고 컨트롤 이름을 **ChartOptions**로 지정한 다음 **추가**를 클릭합니다.  
  
#### 사용자 정의 컨트롤에 라디오 단추를 추가하려면  
  
1.  디자이너에 사용자 정의 컨트롤이 표시되지 않으면 **솔루션 탐색기**에서 **ChartOptions**를 두 번 클릭합니다.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 **Radio Button** 컨트롤을 사용자 정의 컨트롤에 끌어 놓고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**columnChart**|  
    |**텍스트**|Column Chart|  
  
3.  두 번째 라디오 단추를 사용자 정의 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**barChart**|  
    |**텍스트**|가로 막대형 차트|  
  
4.  세 번째 라디오 단추를 사용자 정의 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**lineChart**|  
    |**텍스트**|Line Chart|  
  
5.  네 번째 라디오 단추를 사용자 정의 컨트롤에 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**areaBlockChart**|  
    |**텍스트**|Area Block Chart|  
  
 이제 라디오 단추를 클릭할 때 차트를 업데이트하기 위한 코드를 작성합니다.  
  
## 라디오 단추를 선택할 때 차트 스타일 변경  
 이제 차트 스타일을 변경하는 코드를 추가할 수 있습니다.  이렇게 하려면 사용자 정의 컨트롤에 대한 공용 이벤트를 만들고 선택 형식을 설정하기 위한 속성을 추가하고 각 라디오 단추의 `CheckedChanged` 이벤트에 대한 이벤트 처리기를 만듭니다.  
  
#### 사용자 정의 컨트롤에 대한 이벤트와 속성을 만들려면  
  
1.  **솔루션 탐색기**에서 사용자 정의 컨트롤을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
2.  `SelectionChanged` 이벤트와 `Selection` 속성을 만드는 코드를 `ChartOptions` 클래스에 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#13)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/ChartOptions.vb#13)]  
  
#### 라디오 단추의 CheckedChanged 이벤트를 처리하려면  
  
1.  `areaBlockChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정한 다음 이벤트를 발생시킵니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#14)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#14](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/ChartOptions.vb#14)]  
  
2.  `barChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#15)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/ChartOptions.vb#15)]  
  
3.  `columnChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#16)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#16](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/ChartOptions.vb#16)]  
  
4.  `lineChart` 라디오 단추의 `CheckedChanged` 이벤트 처리기에서 차트 종류를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#17](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#17)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#17](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/ChartOptions.vb#17)]  
  
5.  C\#의 경우 라디오 단추에 대한 이벤트 처리기를 추가해야 합니다.  코드를 `InitializeComponent`에 대한 호출 아래의 `ChartOptions` 생성자에 추가할 수 있습니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/ChartOptions.cs#18)]  
  
## 워크시트에 사용자 정의 컨트롤 추가  
 솔루션을 빌드하면 새 사용자 정의 컨트롤이 **도구 상자**에 자동으로 추가됩니다.  이 컨트롤을 **도구 상자**에서 워크시트로 끌어 놓을 수 있습니다.  
  
#### 워크시트에 사용자 정의 컨트롤을 추가하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **ChartOptions** 사용자 정의 컨트롤이 **도구 상자**에 추가됩니다.  
  
2.  **솔루션 탐색기**에서 **Sheet1.vb** 또는 **Sheet1.cs**를 마우스 오른쪽 단추로 클릭하고 **디자이너 보기**를 클릭합니다.  
  
3.  **도구 상자**에서 **ChartOptions** 컨트롤을 워크시트로 끌어 옵니다.  
  
     `my_Excel_Chart_ChartOptions1`이라는 새 컨트롤이 프로젝트에 추가됩니다.  
  
4.  컨트롤의 이름을 ChartOptions1로 바꿉니다.  
  
## 차트 종류 변경  
 차트 종류를 변경하려면 사용자 정의 컨트롤에 선택된 옵션에 따라 스타일을 설정하는 이벤트 처리기를 만듭니다.  
  
#### 워크시트에 표시되는 차트의 종류를 변경하려면  
  
1.  `Sheet1` 클래스에 다음 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#19](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#19](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#19)]  
  
2.  C\#의 경우 아래와 같이 사용자 정의 컨트롤에 대한 이벤트 처리기를 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트에 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#20)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 라디오 단추를 선택할 때 차트의 스타일이 올바르게 지정되는지 확인할 수 있습니다.  
  
#### 통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  여러 가지 라디오 단추를 선택합니다.  
  
3.  선택한 내용에 맞도록 차트 스타일이 변경되는지 확인합니다.  
  
## 다음 단계  
 이 연습에서는 워크시트에서 라디오 단추와 차트 스타일을 사용하는 기본적인 방법을 보여 줍니다.  이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)을 참조하십시오.  
  
-   단추를 사용하여 텍스트 상자를 채웁니다.  자세한 내용은 [연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)을 참조하십시오.  
  
-   확인란을 사용하여 워크시트의 서식을 변경합니다.  자세한 내용은 [연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)을 참조하십시오.  
  
## 참고 항목  
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)  
  
  