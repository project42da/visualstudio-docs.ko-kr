---
title: 런타임에 Office 문서에 컨트롤 추가
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- host controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- user controls [Office development in Visual Studio], adding at runtime
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], adding at runtime
- helper methods [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: af280d407a8453b66658ee5395a88d2b91b991b7
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="add-controls-to-office-documents-at-runtime"></a>런타임에 Office 문서에 컨트롤 추가
  Microsoft Office Word 문서 및 런타임에 Microsoft Office Excel 통합 문서에 컨트롤을 추가할 수 있습니다. 또한 런타임 시 제거할 수 있습니다. 추가 하거나 런타임에 제거할 이라고 *동적 컨트롤*합니다.  

 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  

 이 항목에서는 다음에 대해 설명합니다.  

-   [컨트롤 컬렉션을 사용 하 여 런타임에 컨트롤 관리](#ControlsCollection)합니다.  

-   [문서 호스트 컨트롤을 추가](#HostControls)합니다.  

-   [문서에 Windows Forms 컨트롤 추가](#WindowsForms)합니다.  

 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 수행 i: 추가 컨트롤을 문서 화면 런타임 시?](http://go.microsoft.com/fwlink/?LinkId=132782)합니다.  

##  <a name="ControlsCollection"></a> 컨트롤 컬렉션을 사용 하 여 런타임에 컨트롤 관리  
 추가 하 고, get, 또는 런타임에 컨트롤을 제거의 도우미 메서드를 사용 하 여 <xref:Microsoft.Office.Tools.Excel.ControlCollection> 및 <xref:Microsoft.Office.Tools.Word.ControlCollection> 개체입니다.  

 이러한 개체에 액세스하는 방법은 개발 중인 프로젝트의 유형에 따라 달라집니다.  

-   Excel용 문서 수준 프로젝트에서는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> , `Sheet1`및 `Sheet2`클래스의 `Sheet3` 속성을 사용합니다. 이러한 클래스에 대 한 자세한 내용은 참조 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)합니다.  

-   Word용 문서 수준 프로젝트에서는 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 클래스의 `ThisDocument` 속성을 사용합니다. 이 클래스에 대 한 자세한 내용은 참조 [문서 호스트 항목](../vsto/document-host-item.md)합니다.  

-   프로그램에서 VSTO 추가 기능 프로젝트에서 Excel 또는 Word에 대 한 사용는 `Controls` 속성은 <xref:Microsoft.Office.Tools.Excel.Worksheet> 또는 <xref:Microsoft.Office.Tools.Word.Document> 런타임에 생성 하는 합니다. 런타임 시 이러한 개체를 생성 하는 방법에 대 한 자세한 내용은 참조 [확장 Word 문서 및 Excel VSTO 추가 기능에서 런타임에 통합](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)합니다.  

### <a name="add-controls"></a>컨트롤 추가  
 <xref:Microsoft.Office.Tools.Excel.ControlCollection> 및 <xref:Microsoft.Office.Tools.Word.ControlCollection> 형식에는 문서 및 워크시트에 호스트 컨트롤 및 공용 Windows Forms 컨트롤을 추가하는 데 사용할 수 있는 도우미 메서드가 포함되어 있습니다. 각 메서드 이름은 `Add`*컨트롤 클래스*형식을 사용합니다. 여기서 *컨트롤 클래스* 는 추가할 컨트롤의 클래스 이름입니다. 예를 들어 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 문서에 추가하려면 <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddNamedRange%2A> 메서드를 사용합니다.  

 다음 코드 예제에서는 Excel용 문서 수준 프로젝트의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 에 `Sheet1` 를 추가합니다.  

 [!code-vb[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#3)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#3)]  

### <a name="access-and-delete-controls"></a>컨트롤 액세스 및 삭제  
 사용할 수는 `Controls` 속성은 <xref:Microsoft.Office.Tools.Excel.Worksheet> 또는 <xref:Microsoft.Office.Tools.Word.Document> 디자인 타임에 추가한 컨트롤을 포함 하 여 문서에서 모든 컨트롤을 반복 하 합니다. 디자인 타임에 추가된 컨트롤을 *정적 컨트롤*이라고 합니다.  

 호출 하 여 동적 컨트롤을 제거할 수는 `Delete` 메서드를 호출 하거나 컨트롤의는 `Remove` 각 컨트롤 컬렉션의 메서드. 다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Excel.ControlCollection.Remove%2A> 메서드를 사용하여 Excel용 문서 수준 프로젝트의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 에서 `Sheet1` 를 제거합니다.  

 [!code-vb[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#4)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#4)]  

 런타임에 정적 컨트롤을 제거할 수 없습니다. 사용 하려는 경우는 `Delete` 또는 `Remove` 가 static 컨트롤을 제거 하는 메서드는 <xref:Microsoft.Office.Tools.CannotRemoveControlException> throw 됩니다.  

> [!NOTE]  
>  문서의 `Shutdown` 이벤트 처리기에서 프로그래밍 방식으로 컨트롤을 제거하지 마세요. `Shutdown` 이벤트가 발생하면 문서의 UI 요소를 더 이상 사용할 수 없습니다. 문서가 닫히기 전에 컨트롤을 제거하려면 <xref:Microsoft.Office.Tools.Word.Document.BeforeClose> 또는 <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> (Word), <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeClose>또는 <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeSave> (Excel)와 같은 다른 이벤트의 이벤트 처리기에 코드를 추가합니다.  

##  <a name="HostControls"></a> 문서에 호스트 컨트롤 추가  
 프로그래밍 방식으로 문서에 호스트 컨트롤을 추가하는 경우 컨트롤을 고유하게 식별하는 이름을 제공해야 하며 문서에서 컨트롤을 추가할 위치를 지정해야 합니다. 구체적인 지침은 다음 항목을 참조하세요.  

-   [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)  

-   [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  

-   [방법: 워크시트에 Chart 컨트롤 추가](../vsto/how-to-add-chart-controls-to-worksheets.md)  

-   [방법: 콘텐츠를 추가 합니다. Word 문서에 컨트롤](../vsto/how-to-add-content-controls-to-word-documents.md)  

-   [방법: Word 문서에 책갈피 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  

 호스트 컨트롤에 대 한 자세한 내용은 참조 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)합니다.  

 문서를 저장하고 닫으면 동적으로 생성된 모든 호스트 컨트롤이 해당 이벤트에서 연결 해제되며 데이터 바인딩 기능이 손실됩니다. 문서를 다시 열 때 호스트 컨트롤을 다시 만드는 코드를 솔루션에 추가할 수 있습니다. 자세한 내용은 참조 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)합니다.  

> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>및 <xref:Microsoft.Office.Tools.Word.XMLNodes>호스트 컨트롤은 프로그래밍 방식으로 문서에 추가할 수 없으므로 해당 컨트롤에 대한 도우미 메서드는 제공되지 않습니다.  

##  <a name="WindowsForms"></a> 문서에 Windows Forms 컨트롤 추가  
 프로그래밍 방식으로 문서에 Windows Forms 컨트롤을 추가하는 경우 컨트롤을 고유하게 식별하는 이름 및 컨트롤의 위치를 제공해야 합니다. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 은 각 컨트롤에 대한 도우미 메서드를 제공합니다. 컨트롤 위치에 대해 범위 또는 특정 좌표를 전달할 수 있도록 이러한 메서드는 오버로드됩니다.  

 문서를 저장하고 닫으면 동적으로 생성된 모든 Windows Forms 컨트롤이 문서에서 제거됩니다. 문서를 다시 열 때 컨트롤을 다시 만드는 코드를 솔루션에 추가할 수 있습니다. VSTO 추가 기능을 사용하여 동적 Windows Forms 컨트롤을 만드는 경우 컨트롤의 ActiveX 래퍼가 문서에 남아 있습니다. 자세한 내용은 참조 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)합니다.  

> [!NOTE]  
>  프로그래밍 방식으로 Windows Forms 컨트롤을 보호된 문서에 추가할 수는 없습니다. 프로그래밍 방식으로 Word 문서 또는 Excel 워크시트의 보호를 해제하여 컨트롤을 추가하는 경우 문서를 닫을 때 컨트롤의 ActiveX 래퍼를 제거하는 추가 코드를 작성해야 합니다. 컨트롤의 ActiveX 래퍼는 보호된 문서에서 자동으로 삭제되지 않습니다.  

### <a name="add-custom-controls"></a>사용자 지정 컨트롤을 추가합니다.  
 사용자 지정 사용자 정의 컨트롤과 같은, 사용 가능한 도우미 메서드에서 지원되지 않는 <xref:System.Windows.Forms.Control> 을 추가하려면 다음 메서드를 사용합니다.  

-   Excel의 경우 <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> 개체의 <xref:Microsoft.Office.Tools.Excel.ControlCollection> 메서드 중 하나를 사용합니다.  

-   Word의 경우 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddControl%2A> 개체의 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드 중 하나를 사용합니다.  

 컨트롤을 추가 하려면 전달 된 <xref:System.Windows.Forms.Control>, 컨트롤에 대 한 위치 및 컨트롤을 고유 하 게 식별 하는 이름을 `AddControl` 메서드. `AddControl` 컨트롤이 워크시트 또는 문서와 상호 작용 하는 방법을 정의 하는 개체를 반환 합니다. `AddControl` 메서드가 반환 되는 <xref:Microsoft.Office.Tools.Excel.ControlSite> (Excel 용) 또는 <xref:Microsoft.Office.Tools.Word.ControlSite> 개체 (Word).  

 다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> 메서드를 사용하여 문서 수준 Excel 프로젝트의 워크시트에 사용자 지정 사용자 정의 컨트롤을 동적으로 추가하는 방법을 보여 줍니다. 이 예제에서 사용자 정의 컨트롤의 이름은 `UserControl1`이고, <xref:Microsoft.Office.Interop.Excel.Range> 의 이름은 `range1`입니다. 이 예제를 사용하려면 프로젝트의 `Sheet`*n* 클래스에서 실행합니다.  

 [!code-vb[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#2)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#2)]  

### <a name="use-members-of-custom-controls"></a>사용자 지정 컨트롤의 멤버를 사용 하 여  
 중 하나를 사용 하 여는 `AddControl` 워크시트 또는 이제 문서에 컨트롤을 추가 하는 메서드는 두 가지 컨트롤 개체가 있습니다.  

-   사용자 지정 컨트롤을 나타내는 <xref:System.Windows.Forms.Control>  

-   `ControlSite`, `OLEObject`, 또는 `OLEControl` 워크시트 또는 문서에 추가 된 후 컨트롤을 나타내는 개체입니다.  

 많은 속성과 메서드가 이러한 컨트롤 간에 공유됩니다. 적절한 컨트롤을 통해 이러한 멤버에 액세스하는 것이 중요합니다.  

-   사용자 지정 컨트롤에만 속하는 멤버에 액세스하려면 <xref:System.Windows.Forms.Control>을 사용합니다.  

-   컨트롤에 의해 공유 되는 멤버에 액세스 하려면 사용 된 `ControlSite`, `OLEObject`, 또는 `OLEControl` 개체입니다.  

 <xref:System.Windows.Forms.Control>에서 공유 멤버에 액세스하는 경우 경고 또는 알림 없이 작업이 실패하거나 잘못된 결과를 생성할 수 있습니다. 메서드 또는 속성을 사용 하 여 항상는 `ControlSite`, `OLEObject`, 또는 `OLEControl` 개체 메서드 또는 속성에 필요한 경우에 사용할 수 없으면; 그런 후에만 참조 해야는 <xref:System.Windows.Forms.Control>합니다.  

 예를 들어 모두는 <xref:Microsoft.Office.Tools.Excel.ControlSite> 클래스 및 <xref:System.Windows.Forms.Control> 클래스는 `Top` 속성입니다. 컨트롤 위쪽과 문서 위쪽 간의 거리를 가져오거나 설정하려면 <xref:Microsoft.Office.Tools.Excel.ControlSite.Top%2A> 의 <xref:Microsoft.Office.Tools.Excel.ControlSite>속성이 아니라 <xref:System.Windows.Forms.Control.Top%2A> 의 <xref:System.Windows.Forms.Control>속성을 사용합니다.  

 [!code-vb[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#3)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#3)]  

## <a name="see-also"></a>참고자료  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [방법: 워크시트에 Chart 컨트롤 추가](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [방법: Word 문서에 책갈피 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Office 문서 개요에서 Windows Forms 컨트롤](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
