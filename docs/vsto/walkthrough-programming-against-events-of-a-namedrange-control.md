---
title: "연습: NamedRange 컨트롤의 이벤트 프로그래밍 | Microsoft Docs"
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
  - "NamedRange 컨트롤, 이벤트"
  - "범위, 이벤트 프로그래밍"
  - "워크시트, 자동화"
  - "워크시트, 셀 값 변경"
  - "워크시트, 이벤트"
ms.assetid: b69676f9-23b2-4ed6-83ab-8868c3f10948
caps.latest.revision: 57
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 56
---
# 연습: NamedRange 컨트롤의 이벤트 프로그래밍
  이 연습에서는 Visual Studio의 Office 개발 도구를 사용하여 Microsoft Office Excel 워크시트에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 추가하고 이 컨트롤의 이벤트를 대상으로 프로그래밍하는 방법을 설명합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습을 통해 다음과 같은 작업 방법을 배웁니다.  
  
-   워크시트에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 추가  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 이벤트에 대한 프로그래밍  
  
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
  
1.  My Named Range Events라는 이름의 Excel 통합 문서 프로젝트를 만듭니다.  **새 문서 만들기**가 선택되어 있는지 확인합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     새로운 Excel 통합 문서가 디자이너에서 열리고 **솔루션 탐색기**에 My Named Range Events 프로젝트가 추가됩니다.  
  
## 워크시트에 텍스트 및 명명된 범위 추가  
 호스트 컨트롤은 확장 Office 개체이므로 네이티브 개체를 추가하는 것과 동일한 방식으로 문서에 추가할 수 있습니다.  예를 들어 **삽입** 메뉴를 열고 **이름**을 가리킨 다음 **정의**를 선택하여 Excel <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 워크시트에 추가할 수 있습니다.  또한 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 **도구 상자**에서 워크시트로 끌어 놓는 방식으로 추가할 수 있습니다.  
  
 이 단계에서는 **도구 상자**를 사용하여 워크시트에 두 개의 NamedRange 컨트롤을 추가한 다음 텍스트를 워크시트에 추가합니다.  
  
#### 워크시트에 범위를 추가하려면  
  
1.  확인은  **내 라는 범위 Events.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 `Sheet1` 표시.  
  
2.  도구 상자의 **Excel 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 `Sheet1`의 **A1** 셀에 끌어 놓습니다.  
  
     그러면 **NamedRange 컨트롤 추가** 대화 상자가 표시됩니다.  
  
3.  편집할 수 있는 텍스트 상자에 **$A$1**이 표시되고 **A1** 셀이 선택되어 있는지 확인합니다.  **A1** 셀이 선택되어 있지 않으면 이 셀을 클릭하여 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
     이제 **A1** 셀은 `namedRange1`이라는 이름을 가진 범위가 됩니다.  범위 추가로 인해 워크시트에 드러나는 변화는 없지만 **A1** 셀을 선택하면 워크시트 왼쪽 위의 **이름** 상자에 범위 이름인 `namedRange1`이 표시됩니다.  
  
5.  **B3** 셀에 또 하나의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 추가합니다.  
  
6.  편집할 수 있는 텍스트 상자에 **$B$3**이 표시되고 **B3** 셀이 선택되어 있는지 확인합니다.  **B3** 셀이 선택되어 있지 않으면 이 셀을 클릭하여 선택합니다.  
  
7.  **확인**을 클릭합니다.  
  
     이제 **B3** 셀은 `namedRange2`이라는 이름을 가진 범위가 됩니다.  
  
#### 워크시트에 텍스트를 추가하려면  
  
1.  **A1** 셀에 다음 텍스트를 입력합니다.  
  
     NamedRange 컨트롤에 대한 예제입니다.  
  
2.  `namedRange2` 왼쪽에 있는 **A3** 셀에 다음 텍스트를 입력합니다.  
  
     이벤트:  
  
 다음 단원에서는 `namedRange1`의 <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>, <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> 및 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 이벤트에 대한 응답으로 `namedRange2`에 텍스트를 삽입하고 `namedRange2` 컨트롤의 속성을 변경하는 코드를 작성합니다.  
  
## BeforeDoubleClick 이벤트에 응답하는 코드 추가  
  
#### BeforeDoubleClick 이벤트를 기반으로 NamedRange2에 텍스트를 삽입하려면  
  
1.  **솔루션 탐색기**에서 **Sheet1.vb** 또는 **Sheet1.cs**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.  
  
2.  다음과 같은 결과가 되도록 `namedRange1_BeforeDoubleClick` 이벤트 처리기에 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#24](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreHostControlsExcel#24](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#24)]  
  
3.  C\#의 경우 아래 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트에서와 같이 명명된 범위에 대한 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#25](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#25)]  
  
## Change 이벤트에 응답하는 코드 추가  
  
#### Change 이벤트를 기반으로 namedRange2에 텍스트를 삽입하려면  
  
1.  다음과 같은 결과가 되도록 `NamedRange1_Change` 이벤트 처리기에 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#26](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreHostControlsExcel#26](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#26)]  
  
    > [!NOTE]  
    >  Excel 범위에 있는 셀을 두 번 클릭하면 편집 모드로 전환되므로, 선택이 범위 밖으로 이동될 때에는 텍스트를 변경하지 않았더라도 <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> 이벤트가 발생합니다.  
  
## SelectionChange 이벤트에 응답하는 코드 추가  
  
#### SelectionChange 이벤트를 기반으로 namedRange2에 텍스트를 삽입하려면  
  
1.  다음과 같은 결과가 되도록 **NamedRange1\_SelectionChange** 이벤트 처리기에 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#27](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreHostControlsExcel#27](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#27)]  
  
    > [!NOTE]  
    >  Excel 범위에 있는 셀을 두 번 클릭하면 선택이 범위 안으로 이동하므로, <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> 이벤트가 발생하기 전에 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 이벤트가 발생합니다.  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 이벤트가 발생하면 그 이벤트에 대해 설명하는 텍스트가 다른 명명된 범위에 삽입되는지 확인할 수 있습니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  `namedRange1`에 커서를 놓은 다음 <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> 이벤트에 관한 텍스트가 삽입되는지와 워크시트에 주석이 삽입되는지를 확인합니다.  
  
3.  `namedRange1` 내부를 두 번 클릭한 다음 <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> 이벤트에 관한 빨간색 기울임꼴 텍스트가 `namedRange2`에 삽입되는지 확인합니다.  
  
4.  다음에는 `namedRange1` 외부를 클릭합니다. 텍스트를 변경하지 않았더라도 편집 모드를 마칠 때 change 이벤트가 발생하는 것을 알 수 있습니다.  
  
5.  `namedRange1` 내에서 텍스트를 변경합니다.  
  
6.  `namedRange1` 외부를 클릭한 다음 <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> 이벤트에 관한 파란색 텍스트가 `namedRange2`에 삽입되는지 확인합니다.  
  
## 다음 단계  
 이 연습에서는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 이벤트에 대한 프로그래밍의 기본을 보여 줍니다.  이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)을 참조하십시오.  
  
## 참고 항목  
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: NamedRange 컨트롤 크기 조정](../vsto/how-to-resize-namedrange-controls.md)   
 [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)  
  
  