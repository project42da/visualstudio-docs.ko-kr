---
title: "런타임에 Word 문서 및 VSTO 추가 기능에서 Excel 통합 문서 확장 | Microsoft Docs"
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
- GetVstoObject method
- application-level add-ins [Office development in Visual Studio], adding controls to documents
- host items [Office development in Visual Studio], creating at run time in add-ins
- application-level add-ins [Office development in Visual Studio], extending Word documents
- application-level add-ins [Office development in Visual Studio], extending Excel workbooks
- controls [Office development in Visual Studio], adding at run time
- HasVstoObject method
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5cd29d7de596704087eb1326791e4fc9df9921a6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time"></a>런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장
  VSTO 추가 기능을 사용하여 다음과 같은 방법으로 Word 문서 및 Excel 통합 문서를 사용자 지정할 수 있습니다.  
  
-   열려 있는 문서 또는 워크시트에 관리되는 컨트롤을 추가합니다.  
  
-   Excel 워크시트의 기존 목록 개체를 이벤트를 표시하고 Windows Forms 데이터 바인딩 모델을 사용하여 데이터에 바인딩될 수 있는 확장된 <xref:Microsoft.Office.Tools.Excel.ListObject> 로 변환합니다.  
  
-   특정 문서, 통합 문서 및 워크시트에 대해 Word 및 Excel에서 표시하는 응용 프로그램 수준 이벤트에 액세스합니다.  
  
 이 기능을 사용하려면 런타임에 문서 또는 통합 문서를 확장하는 개체를 생성합니다.  
  
 **적용 대상:** 이 항목의 정보는 Excel 및 Word의 VSTO 추가 기능 프로젝트에 적용됩니다. 자세한 내용은 [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
## <a name="generating-extended-objects-in-vsto-add-ins"></a>VSTO 추가 기능에서 확장 개체 생성  
 *확장 개체* 는 Visual Studio Tools for Office 런타임에서 제공하는 형식의 인스턴스로, 기본적으로 Word 또는 Excel 개체 모델에 있는 개체( *네이티브 Office 개체*라고 함)에 기능을 추가합니다. Word 또는 Excel 개체에 대 한 확장된 개체를 생성 하려면 GetVstoObject 메서드를 사용 합니다. 처음으로 지정된 된 Word 또는 Excel 개체에 대 한 GetVstoObject 메서드를 호출 하면 지정된 된 개체를 확장 하는 새 개체를 반환 합니다. 메서드를 호출하고 동일한 Word 또는 Excel 개체를 지정할 때마다 동일한 확장 개체가 반환됩니다.  
  
 확장 개체의 형식은 네이티브 Office 개체의 형식과 동일한 이름을 사용하지만 형식은 <xref:Microsoft.Office.Tools.Excel> 또는 <xref:Microsoft.Office.Tools.Word> 네임스페이스에 정의되어 있습니다. 예를 들어를 확장 하려면 GetVstoObject 메서드를 호출 하는 경우는 <xref:Microsoft.Office.Interop.Word.Document> 개체를 반환 하는 메서드는 <xref:Microsoft.Office.Tools.Word.Document> 개체입니다.  
  
 GetVstoObject 메서드는 기본적으로 VSTO 추가 기능 프로젝트에서 사용 하는 데 사용 됩니다. 문서 수준 프로젝트에서 이러한 메서드를 사용할 수도 있지만 다르게 동작하며 더 적게 사용됩니다.  
  
 확장된 개체가 특정 네이티브 Office 개체에 대 한 이미 생성 된 여부를 확인 하려면 HasVstoObject 메서드를 사용 합니다. 자세한 내용은 [Office 개체가 확장되었는지 확인](#HasVstoObject)을 참조하세요.  
  
### <a name="generating-host-items"></a>호스트 항목 생성  
 GetVstoObject는 문서 수준 개체 확장을 사용 하는 경우 (즉, 한 <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, 또는 <xref:Microsoft.Office.Interop.Word.Document>), 반환된 된 개체 라고는 *호스트 항목*합니다. 호스트 항목은 다른 확장 개체 및 컨트롤을 비롯하여 다른 개체를 포함할 수 있는 형식입니다. 이 형식은 Word 또는 Excel 주 interop 어셈블리의 해당 형식과 유사하지만 추가 기능을 제공합니다. 호스트 항목에 대한 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)를 참조하세요.  
  
 호스트 항목을 생성한 후에는 문서, 통합 문서 또는 워크시트에 관리되는 컨트롤을 추가하는 데 사용할 수 있습니다. 자세한 내용은 [문서 및 워크시트에 관리되는 컨트롤 추가](#AddControls)를 참조하세요.  
  
##### <a name="to-generate-a-host-item-for-a-word-document"></a>Word 문서에 대한 호스트 항목을 생성하려면  
  
-   다음 코드 예제에서는 활성 문서에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.  
  
     [!code-vb[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#8)]
     [!code-csharp[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#8)]  
  
##### <a name="to-generate-a-host-item-for-an-excel-workbook"></a>Excel 통합 문서에 대한 호스트 항목을 생성하려면  
  
-   다음 코드 예제에서는 활성 통합 문서에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#2)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#2)]  
  
##### <a name="to-generate-a-host-item-for-an-excel-worksheet"></a>Excel 워크시트에 대한 호스트 항목을 생성하려면  
  
-   다음 코드 예제에서는 프로젝트의 활성 워크시트에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#1)]  
  
### <a name="generating-listobject-host-controls"></a>ListObject 호스트 컨트롤 생성  
 확장할 GetVstoObject 메서드를 사용 하면 한 <xref:Microsoft.Office.Interop.Excel.ListObject>, 메서드가 반환는 <xref:Microsoft.Office.Tools.Excel.ListObject>합니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 에는 원래 <xref:Microsoft.Office.Interop.Excel.ListObject>의 모든 기능이 있을 뿐만 아니라 Windows Forms 데이터 바인딩 모델을 사용하여 데이터에 바인딩하는 기능과 같은 추가 기능도 있습니다. 자세한 내용은 [ListObject Control](../vsto/listobject-control.md)을 참조하세요.  
  
##### <a name="to-generate-a-host-control-for-a-listobject"></a>ListObject에 대한 호스트 컨트롤을 생성하려면  
  
-   다음 코드 예제에서는 프로젝트의 활성 워크시트에서 첫 번째 <xref:Microsoft.Office.Tools.Excel.ListObject> 에 대해 <xref:Microsoft.Office.Interop.Excel.ListObject> 를 생성하는 방법을 보여 줍니다.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#3)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#3)]  
  
##  <a name="AddControls"></a> 문서 및 워크시트에 관리되는 컨트롤 추가  
 <xref:Microsoft.Office.Tools.Word.Document> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet>를 생성한 후 이러한 확장 개체가 나타내는 문서 또는 워크시트에 컨트롤을 추가할 수 있습니다. 이 위해의 컨트롤 속성을 사용 하 여는 <xref:Microsoft.Office.Tools.Word.Document> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet>합니다. 자세한 내용은 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
 Windows Forms 컨트롤 또는 *호스트 컨트롤*을 추가할 수 있습니다. 호스트 컨트롤은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 에서 제공하는 컨트롤로, Word 또는 Excel 주 interop 어셈블리에서 해당 컨트롤을 래핑합니다. 호스트 컨트롤은 기본 네이티브 Office 개체의 모든 동작을 표시할 뿐만 아니라 이벤트를 발생시키고 Windows Forms 데이터 바인딩 모델을 사용하여 데이터에 바인딩될 수도 있습니다. 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)을 참조하십시오.  
  
> [!NOTE]  
>  VSTO 추가 기능을 사용하여 워크시트에 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤을 추가하거나 문서에 <xref:Microsoft.Office.Tools.Word.XMLNode> 또는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤을 추가할 수는 없습니다. 이러한 호스트 컨트롤은 프로그래밍 방식으로 추가할 수 없습니다. 자세한 내용은 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하세요.  
  
### <a name="persisting-and-removing-controls"></a>컨트롤 유지 및 제거  
 문서 또는 워크시트에 관리되는 컨트롤을 추가하는 경우 문서를 저장한 후 닫으면 컨트롤이 유지되지 않습니다. 호스트 컨트롤은 모두 제거되고 기본 네이티브 Office 개체만 남겨집니다. 예를 들어 <xref:Microsoft.Office.Tools.Excel.ListObject> 가 <xref:Microsoft.Office.Interop.Excel.ListObject>가 됩니다. Windows Forms 컨트롤도 모두 제거되지만 컨트롤의 ActiveX 래퍼는 문서에 남겨집니다. 컨트롤을 정리하거나 다음에 문서를 열 때 컨트롤을 다시 만들려면 VSTO 추가 기능에 코드를 포함해야 합니다. 자세한 내용은 [Persisting Dynamic Controls in Office Documents](../vsto/persisting-dynamic-controls-in-office-documents.md)을 참조하세요.  
  
## <a name="accessing-application-level-events-on-documents-and-workbooks"></a>문서 및 통합 문서에서 응용 프로그램 수준 이벤트에 액세스  
 네이티브 Word 및 Excel 개체 모델에서 일부 문서, 통합 문서 및 워크시트 이벤트는 응용 프로그램 수준에서만 발생합니다. 예를 들어 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트는 Word에서 문서를 열 때 발생하지만 이 이벤트는 <xref:Microsoft.Office.Interop.Word.Application> 클래스가 아닌 <xref:Microsoft.Office.Interop.Word.Document> 클래스에 정의되어 있습니다.  
  
 VSTO 추가 기능에서 네이티브 Office 개체만 사용하는 경우 이러한 응용 프로그램 수준 이벤트를 처리한 다음 추가 코드를 작성하여 이벤트가 발생한 문서가 사용자 지정한 문서인지를 확인해야 합니다. 호스트 항목은 이러한 이벤트를 문서 수준에서 제공하므로 특정 문서에 대한 이벤트를 더 쉽게 처리할 수 있습니다. 호스트 항목을 생성한 다음 해당 호스트 항목에 대한 이벤트를 처리 할 수 있습니다.  
  
### <a name="example-that-uses-native-word-objects"></a>네이티브 Word 개체를 사용하는 예제  
 다음 코드 예제에서는 Word 문서에 대한 응용 프로그램 수준 이벤트를 처리하는 방법을 보여 줍니다. `CreateDocument` 메서드는 새 문서를 만든 다음 이 문서가 저장되지 않도록 하는 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트 처리기를 정의합니다. 이 이벤트는 <xref:Microsoft.Office.Interop.Word.Application> 개체에 대해 발생되는 응용 프로그램 수준 이벤트이므로 이벤트 처리기에서 `Doc` 매개 변수를 `document1` 개체와 비교하여 `document1` 이 저장된 문서를 나타내는지 확인해야 합니다  
  
 [!code-vb[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#12)]
 [!code-csharp[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#12)]  
  
### <a name="examples-that-use-a-host-item"></a>호스트 항목을 사용하는 예제  
 다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document> 이벤트를 처리하여 이 프로세스를 간소화합니다. 이러한 예제에서 `CreateDocument2` 메서드는 <xref:Microsoft.Office.Tools.Word.Document> 개체를 확장하는 `document2` 를 생성한 다음 문서가 저장되지 않도록 하는 <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> 이벤트 처리기를 정의합니다. 이 이벤트 처리기는 `document2` 가 저장되는 경우에만 호출되므로 저장된 문서를 확인하는 추가 작업을 수행하지 않고도 저장 작업을 취소할 수 있습니다.  
  
 다음 코드 예제에서는 이 작업을 보여 줍니다.  
  
 [!code-vb[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#13)]
 [!code-csharp[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#13)]  
  
##  <a name="HasVstoObject"></a> Office 개체가 확장되었는지 확인  
 확장된 개체가 특정 네이티브 Office 개체에 대 한 이미 생성 된 여부를 확인 하려면 HasVstoObject 메서드를 사용 합니다. 이 메서드는 확장 개체가 이미 생성된 경우 **true** 를 반환하고, 그렇지 않은 경우 **false**를 반환합니다.  
  
 Globals.Factory.HasVstoMethod 방법을 사용 합니다. 확장 개체에 대해 테스트하려는 네이티브 Word 또는 Excel 개체(예: <xref:Microsoft.Office.Interop.Word.Document> 또는 <xref:Microsoft.Office.Interop.Excel.Worksheet>)를 전달합니다.  
  
 HasVstoObject 메서드를 지정된 된 Office 개체에 확장된 개체가 있는 경우에 코드를 실행 하려는 경우 유용 합니다. 예를 들어 Word VSTO 추가 기능을 처리 하는 경우는 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 저장 전에 해당 문서에서 관리 되는 컨트롤을 제거 하는 이벤트, HasVstoObject 메서드를 사용 하 여 문서가 확장 되었는지 여부를 확인 하려면. 문서가 확장되지 않은 경우 관리되는 컨트롤을 포함할 수 없으므로 이벤트 처리기는 문서에서 컨트롤을 정리하려고 하지 않고도 반환할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)  
  
  