---
title: "방법: Office 문서에 Windows Forms 컨트롤 추가"
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
  - "컨트롤[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "문서[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "Office 문서[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], 추가"
ms.assetid: 4d188ad2-8e17-4eb0-8422-2ff56c683e3d
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 방법: Office 문서에 Windows Forms 컨트롤 추가
  디자인 타임에 문서 수준 프로젝트에서 Microsoft Office Excel 및 Microsoft Office Word 문서에 Windows Forms 컨트롤을 추가할 수 있습니다.  런타임에 문서 수준 사용자 지정 및 VSTO 추가 기능에서 컨트롤을 추가할 수 있습니다.  예를 들어 사용자가 옵션 목록에서 선택할 수 있도록 워크시트에 <xref:Microsoft.Office.Tools.Excel.Controls.ComboBox> 컨트롤을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 컨트롤 추가](#designtime)  
  
-   [런타임에 문서 수준 프로젝트에서 컨트롤 추가](#runtimedoclevel)  
  
-   [런타임에 VSTO 추가 기능에서 컨트롤 추가](#runtimeaddin)  
  
 ![비디오에 링크](~/data-tools/media/playvideo.gif "비디오에 링크") 관련 동영상 데모를 보려면 [어떻게 할까요?: 런타임에 문서 화면에 컨트롤 추가](http://go.microsoft.com/fwlink/?LinkId=132782)\(영문\)를 참조하세요.  
  
##  <a name="designtime"></a> 디자인 타임에 컨트롤 추가  
 디자인 타임에 문서 수준 프로젝트의 문서에 Windows Forms 컨트롤을 추가하는 여러 가지 방법이 있습니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### Windows Forms 컨트롤을 문서로 끌어오려면  
  
1.  문서가 디자이너에 표시되도록 Visual Studio에서 Excel 통합 문서 프로젝트 또는 Word 문서 프로젝트를 만들거나 엽니다.  프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 추가할 컨트롤을 클릭하고 문서로 끌어옵니다.  
  
    > [!NOTE]  
    >  Excel에서 컨트롤을 선택하는 경우 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
#### 문서에서 Windows Forms 컨트롤을 그리려면  
  
1.  문서가 디자이너에 표시되도록 Visual Studio에서 Excel 통합 문서 프로젝트 또는 Word 문서 프로젝트를 만들거나 엽니다.  프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 추가할 컨트롤을 클릭합니다.  
  
3.  문서에서 컨트롤의 왼쪽 위를 배치할 위치를 클릭한 다음 컨트롤의 오른쪽 아래를 배치할 위치로 끕니다.  
  
     지정된 위치와 크기를 사용하여 컨트롤이 문서에 추가됩니다.  
  
    > [!NOTE]  
    >  Excel에서 컨트롤을 선택하는 경우 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
#### 컨트롤을 한 번 클릭하여 문서에 Windows Forms 컨트롤을 추가하려면  
  
1.  문서가 디자이너에 표시되도록 Visual Studio에서 Excel 통합 문서 프로젝트 또는 Word 문서 프로젝트를 만들거나 엽니다.  프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 추가할 컨트롤을 클릭합니다.  
  
3.  문서에서 컨트롤을 추가할 위치를 클릭합니다.  
  
     기본 크기를 사용하여 컨트롤이 문서에 추가됩니다.  
  
    > [!NOTE]  
    >  Excel에서 컨트롤을 선택하는 경우 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
#### 컨트롤을 두 번 클릭하여 문서에 Windows Forms 컨트롤을 추가하려면  
  
1.  문서가 디자이너에 표시되도록 Visual Studio에서 Excel 통합 문서 프로젝트 또는 Word 문서 프로젝트를 만들거나 엽니다.  프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 추가할 컨트롤을 두 번 클릭합니다.  
  
     컨트롤의 문서 또는 활성 창의 가운데에 추가됩니다.  
  
    > [!NOTE]  
    >  Excel에서 컨트롤을 선택하는 경우 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
#### Enter 키를 눌러 문서에 Windows Forms 컨트롤을 추가하려면  
  
1.  문서가 디자이너에 표시되도록 Visual Studio에서 Excel 통합 문서 프로젝트 또는 Word 문서 프로젝트를 만들거나 엽니다.  프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 추가할 컨트롤을 클릭하고 Enter 키를 누릅니다.  
  
     컨트롤의 문서 또는 활성 창의 가운데에 추가됩니다.  
  
    > [!NOTE]  
    >  Excel에서 컨트롤을 선택하는 경우 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에서 컨트롤 추가  
 프로그래밍 방식으로 런타임에 Windows Forms 컨트롤을 문서에 추가할 수 있습니다.  Word에서 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.DocumentBase.Controls%2A> 속성 메서드를 사용합니다.  Excel에서 `Sheet`*n* 클래스의 <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Controls%2A> 속성 메서드를 사용합니다.  각 메서드에는 다양한 방법으로 컨트롤의 위치를 지정할 수 있는 여러 오버로드가 있습니다.  
  
 런타임에 Windows Forms 컨트롤을 문서에 추가할 경우 문서를 닫으면 컨트롤이 문서에 유지되지 않습니다.  다음에 문서를 열 때 컨트롤을 다시 만들 수 있습니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
#### 런타임에 Windows Forms 컨트롤을 추가하려면  
  
1.  이름이 Add\<*컨트롤 클래스*\>인 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 Windows Forms 컨트롤의 클래스 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>\)입니다.  
  
     다음 코드 예제에서는 Excel용 문서 수준 프로젝트에서 `Sheet1`의 **C5** 셀에 <xref:Microsoft.Office.Tools.Excel.Controls.Button>을 추가하는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#4)]  
  
##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능에서 컨트롤 추가  
 프로그래밍 방식으로 런타임에 열려 있는 문서에 Windows Forms 컨트롤을 추가할 수 있습니다.  먼저, 열려 있는 문서 또는 워크시트의 기반이 되는 호스트 항목을 생성합니다.  그런 다음 Word에서 새 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 속성 메서드를 사용합니다.  Excel에서 새 호스트 항목의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> 속성 메서드를 사용합니다.  각 메서드에는 다양한 방법으로 컨트롤의 위치를 지정할 수 있는 여러 오버로드가 있습니다.  
  
 런타임에 Windows Forms 컨트롤을 문서에 추가할 경우 문서를 닫으면 컨트롤이 문서에 유지되지 않습니다.  다음에 문서를 열 때 컨트롤을 다시 만들 수 있습니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
 VSTO 추가 기능 프로젝트에서 호스트 항목을 생성하는 방법에 대한 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
#### 런타임에 Windows Forms 컨트롤을 추가하려면  
  
1.  이름이 Add\<*컨트롤 클래스*\>인 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 Windows Forms 컨트롤의 클래스 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>\)입니다.  
  
    > [!NOTE]  
    >  [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 VSTO 추가 기능 프로젝트에서 Add\<*컨트롤 클래스*\> 메서드에 액세스하려면 먼저 Microsoft.Office.Tools.Excel.v4.0.Utilities.dll 또는 Microsoft.Office.Tools.Word.v4.0.Utilities.dll 어셈블리에 대한 참조를 추가해야 합니다.  
  
     다음 코드 예제에서는 Word VSTO 추가 기능을 사용하여 활성 문서의 첫 번째 단락에 <xref:Microsoft.Office.Tools.Word.Controls.Button>을 추가하는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#7)]
     [!code-vb[Trin_WordAddInDynamicControls#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#7)]  
  
## 참고 항목  
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  