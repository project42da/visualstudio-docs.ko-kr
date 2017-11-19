---
title: "방법: 프로그래밍 방식으로 추가 하 고 워크시트 메모를 삭제 합니다. | Microsoft Docs"
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
- ranges, comments
- worksheets, comments
- comments, worksheets
ms.assetid: 3408ce22-a7b7-4e2b-bfc1-dc24d679ee73
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c2c9e2111e02bb9669b7e915bb170e4607932978
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-add-and-delete-worksheet-comments"></a>방법: 프로그래밍 방식으로 워크시트 메모 추가 및 삭제
  프로그래밍 방식으로 Microsoft Office Excel 워크시트에서 메모를 추가하거나 삭제할 수 있습니다. 메모는 다중 셀 범위가 아닌 단일 셀에만 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="adding-and-deleting-a-comment-in-a-document-level-project"></a>문서 수준 프로젝트에서 메모 추가 및 삭제  
 다음 예제에서는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 단일 셀 `dateComment` 컨트롤이 `Sheet1`이라는 워크시트에 있다고 가정합니다.  
  
#### <a name="to-add-a-new-comment-to-a-named-range"></a>명명된 범위에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> 컨트롤의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 메서드를 호출하고 메모 텍스트를 제공합니다. 이 코드는 `Sheet1` 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#30)]  
  
#### <a name="to-delete-a-comment-from-a-named-range"></a>명명된 범위에서 메모를 삭제하려면  
  
1.  메모가 해당 범위에 있는지 확인하고 삭제합니다. 이 코드는 `Sheet1` 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#29)]  
  
## <a name="adding-and-deleting-a-comment-in-an-vsto-add-in-project"></a>VSTO 추가 기능 프로젝트에서 메모 추가 및 삭제  
 다음 예제에서는 <xref:Microsoft.Office.Interop.Excel.Range> 라는 단일 셀 `dateComment` 가 활성 워크시트에 있다고 가정합니다.  
  
#### <a name="to-add-a-new-comment-to-an-excel-range"></a>Excel 범위에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> 의 <xref:Microsoft.Office.Interop.Excel.Range> 메서드를 호출하여 메모 텍스트를 제공합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#20)]  
  
#### <a name="to-delete-a-comment-from-an-excel-range"></a>Excel 범위에서 메모를 삭제하려면  
  
1.  메모가 해당 범위에 있는지 확인하고 삭제합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#19)]  
  
## <a name="see-also"></a>참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 메모 표시](../vsto/how-to-programmatically-display-worksheet-comments.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)  
  
  