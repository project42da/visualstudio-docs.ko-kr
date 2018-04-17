---
title: '방법: 프로그래밍 방식으로 통합 문서를 저장 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, saving in XML format
- workbooks, saving
- workbooks, saving backup copies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4f3421c5a00d062fb49cc73b8a7f2ba592dc5d74
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-save-workbooks"></a>방법: 프로그래밍 방식으로 통합 문서 저장
  통합 문서를 저장하는 방법에는 여러 가지가 있습니다. 경로를 변경하지 않고 통합 문서를 저장할 수 있습니다. 통합 문서가 이전에 저장되지 않은 경우 경로를 지정하여 통합 문서를 저장해야 합니다. 명시적 경로 없이 Microsoft Office Excel은 파일을 만들 때 지정된 이름으로 현재 폴더에 파일을 저장합니다. 메모리에 열려 있는 통합 문서를 수정하지 않고 통합 문서의 복사본을 저장할 수도 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="saving-a-workbook-without-changing-the-path"></a>경로를 변경하지 않고 통합 문서 저장  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  ThisWorkbook 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#4)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> 메서드를 호출하여 활성 통합 문서를 저장합니다. 다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="saving-a-workbook-with-a-new-path"></a>새 경로를 사용하여 통합 문서 저장  
 필요에 따라 파일 형식, 암호, 액세스 모드 등을 지정하여 지정된 통합 문서를 새 위치나 새 이름으로 저장할 수 있습니다.  
  
> [!NOTE]  
>  설정 하려는 경우는 <xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A> 속성을 **False** 전에 일부 형식으로 저장 하기 때문에 새 경로 사용 하 여 통합 문서를 저장 하려면 조작이 필요 합니다. 이 속성을 설정 **False** 를 사용 하면 모든 기본값을 사용 하도록 Excel입니다.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> 메서드를 호출합니다. 다음 코드 예제를 사용하려면 `ThisWorkbook` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#5)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> 메서드를 호출하여 활성 통합 문서를 새 경로에 저장합니다. 다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="saving-a-copy-of-the-workbook"></a>통합 문서의 복사본 저장  
 메모리에 열려 있는 통합 문서를 수정하지 않고 통합 문서의 복사본을 파일에 저장할 수 있습니다. 이 기능은 통합 문서의 위치를 수정하지 않고 백업 복사본을 만들려는 경우에 유용합니다.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> 메서드를 호출합니다. 다음 코드 예제를 사용하려면 `ThisWorkbook` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#6)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> 메서드를 호출하여 활성 통합 문서의 복사본을 저장합니다. 다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 통합 문서를 저장하거나 복사하는 메서드를 대화형으로 취소하면 코드에서 런타임 오류가 발생합니다. 예를 들어, 프로시저를 호출 하는 경우는 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> 메서드 하지만 Excel에서 라는 메시지가 표시 되지 않도록 설정 않습니다 사용자가 **취소** 런타임에 오류 발생 대화 상자가 나타나면 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  