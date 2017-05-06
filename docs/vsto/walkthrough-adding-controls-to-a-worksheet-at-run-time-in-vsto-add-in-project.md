---
title: "연습: 런타임에 VSTO 추가 기능 프로젝트에서 워크시트에 컨트롤 추가"
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
  - "추가 기능[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "응용 프로그램 수준 추가 기능[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "컨트롤[Visual Studio에서 Office 개발], 런타임에 워크시트에 추가"
  - "워크시트, 런타임에 컨트롤 추가"
ms.assetid: 4f68677a-4789-4564-b229-02e2d4031a5f
caps.latest.revision: 38
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 37
---
# 연습: 런타임에 VSTO 추가 기능 프로젝트에서 워크시트에 컨트롤 추가
  Excel VSTO 추가 기능을 사용하여 열려 있는 워크시트에 컨트롤을 추가할 수 있습니다.  이 연습에서는 리본 메뉴를 사용하여 사용자가 <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange> 및 <xref:Microsoft.Office.Tools.Excel.ListObject>를 워크시트에 추가할 수 있도록 하는 방법을 보여 줍니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
 **적용 대상:** 이 항목의 정보는 Excel용 VSTO 추가 기능 프로젝트에 적용됩니다.  자세한 내용은 [Office 응용 프로그램 및 프로젝트 형식에 따라 사용 가능한 기능](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   워크시트에 컨트롤을 추가하는 UI\(사용자 인터페이스\) 제공  
  
-   워크시트에 컨트롤 추가  
  
-   워크시트에서 컨트롤 제거  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Excel  
  
## 새 Excel VSTO 추가 기능 프로젝트 만들기  
 먼저 Excel VSTO 추가 기능 프로젝트를 만듭니다.  
  
#### 새 Excel VSTO 추가 기능 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 이름이 ExcelDynamicControls인 Excel VSTO 추가 기능 프로젝트를 만듭니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **Microsoft.Office.Tools.Excel.v4.0.Utilities.dll** 어셈블리에 대한 참조를 추가합니다.  이 참조는 이 연습의 뒷부분에서 프로그래밍 방식으로 워크시트에 Windows Forms 컨트롤을 추가하는 데 필요합니다.  
  
## 워크시트에 컨트롤을 추가하는 UI 제공  
 Excel 리본 메뉴에 사용자 지정 탭을 추가합니다.  사용자는 탭에서 확인란을 선택하여 워크시트에 컨트롤을 추가할 수 있습니다.  
  
#### 워크시트에 컨트롤을 추가하는 UI를 제공하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **리본\(비주얼 디자이너\)**을 선택하고 **추가**를 클릭합니다.  
  
     **Ribbon1.cs** 또는 **Ribbon1.vb**라는 파일이 리본 디자이너에서 열리고 기본 탭과 그룹을 표시합니다.  
  
3.  **도구 상자**의 **Office 리본 컨트롤** 탭에서 CheckBox 컨트롤을 **group1**로 끌어옵니다.  
  
4.  **CheckBox1**을 클릭하여 선택합니다.  
  
5.  **속성** 창에서 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|단추|  
    |**레이블**|단추|  
  
6.  **group1**에 두 번째 확인란을 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|NamedRange|  
    |**레이블**|NamedRange|  
  
7.  **group1**에 세 번째 확인란을 추가하고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|ListObject|  
    |**레이블**|ListObject|  
  
## 워크시트에 컨트롤 추가  
 관리되는 컨트롤은 컨테이너 역할을 하는 호스트 항목에만 추가할 수 있습니다.  VSTO 추가 기능 프로젝트는 열려 있는 모든 통합 문서를 사용하기 때문에 컨트롤을 추가하기 전에 VSTO 추가 기능에서 워크시트를 호스트 항목으로 변환하거나 기존 호스트 항목을 가져옵니다.  각 컨트롤의 클릭 이벤트 처리기에 코드를 추가하여 열려 있는 워크시트를 기반으로 하는 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 생성합니다.  그런 다음 워크시트의 현재 선택 영역에 <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange> 및 <xref:Microsoft.Office.Tools.Excel.ListObject>를 추가합니다.  
  
#### 워크시트에 컨트롤을 추가하려면  
  
1.  리본 디자이너에서 **Button**을 두 번 클릭합니다.  
  
     **Button** 확인란의 <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> 이벤트 처리기가 코드 편집기에서 열립니다.  
  
2.  `Button_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     이 코드는 `GetVstoObject` 메서드를 사용하여 통합 문서의 첫 번째 워크시트를 나타내는 호스트 항목을 가져온 다음 현재 선택된 셀에 <xref:Microsoft.Office.Tools.Excel.Controls.Button> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/Ribbon1.cs#2)]
     [!code-vb[Trin_Excel_Dynamic_Controls#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/Ribbon1.vb#2)]  
  
3.  **솔루션 탐색기**에서 Ribbon1.cs 또는 Ribbon1.vb를 선택합니다.  
  
4.  **보기** 메뉴에서 **디자이너**를 클릭합니다.  
  
5.  리본 디자이너에서 **NamedRange**를 두 번 클릭합니다.  
  
6.  `NamedRange_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     이 코드는 `GetVstoObject` 메서드를 사용하여 통합 문서의 첫 번째 워크시트를 나타내는 호스트 항목을 가져온 다음 현재 선택된 셀에 대한 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 정의합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/Ribbon1.cs#3)]
     [!code-vb[Trin_Excel_Dynamic_Controls#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/Ribbon1.vb#3)]  
  
7.  리본 디자이너에서 **ListObject**를 두 번 클릭합니다.  
  
8.  `ListObject_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     이 코드는 `GetVstoObject` 메서드를 사용하여 통합 문서의 첫 번째 워크시트를 나타내는 호스트 항목을 가져온 다음 현재 선택된 셀에 대한 <xref:Microsoft.Office.Tools.Excel.ListObject>를 정의합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/Ribbon1.cs#4)]
     [!code-vb[Trin_Excel_Dynamic_Controls#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/Ribbon1.vb#4)]  
  
9. 리본 코드 파일 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/Ribbon1.cs#1)]
     [!code-vb[Trin_Excel_Dynamic_Controls#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/Ribbon1.vb#1)]  
  
## 워크시트에서 컨트롤 제거  
 워크시트를 저장하고 닫을 때 컨트롤은 유지되지 않습니다.  워크시트를 저장하기 전에 프로그래밍 방식으로 생성된 모든 Windows Forms 컨트롤을 제거해야 합니다. 그렇지 않으면 통합 문서를 다시 열 때 컨트롤의 윤곽만 나타납니다.  생성된 호스트 항목의 컨트롤 컬렉션에서 Windows Forms 컨트롤을 제거하는 코드를 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> 이벤트에 추가합니다.  자세한 내용은 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)를 참조하세요.  
  
#### 워크시트에서 컨트롤을 제거하려면  
  
1.  **솔루션 탐색기**에서 ThisAddIn.cs 또는 ThisAddIn.vb를 선택합니다.  
  
2.  **보기** 메뉴에서 **코드**를 클릭합니다.  
  
3.  ThisAddIn 클래스에 다음 메서드를 추가합니다.  이 코드는 통합 문서에서 첫 번째 워크시트를 가져온 다음 `HasVstoObject` 메서드를 사용하여 워크시트에 생성된 워크시트 개체가 있는지 여부를 확인합니다.  생성된 워크시트 개체에 컨트롤이 있는 경우 코드가 해당 워크시트 개체를 가져온 다음 컨트롤 컬렉션을 반복하고 컨트롤을 제거합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#6)]
     [!code-vb[Trin_Excel_Dynamic_Controls#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#6)]  
  
4.  C\#에서는 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> 이벤트에 대한 이벤트 처리기를 만들어야 합니다.  `ThisAddIn_Startup` 메서드에 이 코드를 배치할 수 있습니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하세요.  `ThisAddIn_Startup` 메서드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#5)]  
  
## 솔루션 테스트  
 리본 메뉴의 사용자 지정 탭에서 선택하여 워크시트에 컨트롤을 추가합니다.  워크시트를 저장하면 이러한 컨트롤이 제거됩니다.  
  
#### 솔루션을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  Sheet1에서 임의 셀을 선택합니다.  
  
3.  **추가 기능** 탭을 클릭합니다.  
  
4.  **group1** 그룹에서 **Button**을 클릭합니다.  
  
     선택한 셀에 단추가 나타납니다.  
  
5.  Sheet1에서 다른 셀을 선택합니다.  
  
6.  **group1** 그룹에서 **NamedRange**를 클릭합니다.  
  
     선택한 셀에 대해 명명된 범위가 정의됩니다.  
  
7.  Sheet1에서 일련의 셀을 선택합니다.  
  
8.  **group1** 그룹에서 **ListObject**를 클릭합니다.  
  
     선택한 셀에 대해 목록 개체가 추가됩니다.  
  
9. 워크시트를 저장합니다.  
  
     Sheet1에 추가한 컨트롤이 더 이상 나타나지 않습니다.  
  
## 다음 단계  
 다음 항목에서 Excel VSTO 추가 기능 프로젝트의 컨트롤에 대해 자세히 알아볼 수 있습니다.  
  
-   워크시트에 컨트롤을 저장하는 방법을 알아보려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)에서 Excel VSTO 추가 기능 동적 컨트롤 샘플을 참조하세요.  
  
## 참고 항목  
 [Excel 솔루션](../vsto/excel-solutions.md)   
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)  
  
  