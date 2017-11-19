---
title: "방법: 프로그래밍 방식으로 통합 문서를 보호 | Microsoft Docs"
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
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
ms.assetid: 553c67b9-e2a4-46b6-878c-5b4b4efa4589
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7dcbedb2c30758c762af0c301c239dd03fe4b10f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-protect-workbooks"></a>방법: 프로그래밍 방식으로 통합 문서 보호
  사용자 수 없는 추가 하거나 워크시트를 삭제 하 고 또한 프로그래밍 방식으로 통합 문서를 보호 해제 되도록 Microsoft Office Excel 통합 문서를 보호할 수 있습니다. 필요에 따라 암호를 지정 하, 여부를 나타낼 있습니다 (사용자가 시트를 이동할 수 없습니다) 되므로 보호 구조를 보호 하는 통합 문서의 창을 표시할지 여부를 지정 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 통합 문서를 보호 하는 셀을 편집 하 여 사용자가 중지 되지 않습니다. 데이터를 보호 하려면 워크시트를 보호 해야 합니다. 자세한 내용은 참조 [하는 방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)합니다.  
  
 다음 코드 예제에서는 변수를 사용 하 여 사용자에 게 서 가져온 암호가 포함 합니다.  
  
## <a name="protecting-a-workbook-that-is-part-of-a-document-level-customization"></a>통합 문서 수준 사용자 지정의 일부인 문서 보호  
  
#### <a name="to-protect-a-workbook"></a>통합 문서를 보호 하려면  
  
1.  호출의 <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> 메서드 통합 문서의 암호입니다. 다음 코드 예제를 사용 하려면에서 실행 된 `ThisWorkbook` 시트 클래스에 없는 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
#### <a name="to-unprotect-a-workbook"></a>통합 문서 보호를 해제 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> 메서드를 필요한 경우 암호를 전달 합니다. 다음 코드 예제를 사용 하려면에서 실행 된 `ThisWorkbook` 시트 클래스에 없는 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protecting-a-workbook-by-using-an-application-level-add-in"></a>응용 프로그램 수준 추가 기능을 사용 하 여 통합 문서를 보호 합니다.  
  
#### <a name="to-protect-a-workbook"></a>통합 문서를 보호 하려면  
  
1.  호출의 <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> 메서드 통합 문서의 암호입니다. 이 코드 예제에서는 활성 통합 문서를 사용 합니다. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
#### <a name="to-unprotect-a-workbook"></a>통합 문서 보호를 해제 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> 필요한 경우 암호를 전달 하 여 활성 통합 문서의 메서드. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  