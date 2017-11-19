---
title: "방법: 프로그래밍 방식으로 워크시트를 인쇄 | Microsoft Docs"
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
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
ms.assetid: 312bfcd7-0a74-421c-b42e-df71a06b7bdf
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 030580d2db7490a7ce806cca86477659a0b00267
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-print-worksheets"></a>방법: 프로그래밍 방식으로 워크시트 인쇄
  통합 문서의 모든 워크시트를 인쇄할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="printing-a-worksheet-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 워크시트 인쇄  
  
#### <a name="to-print-a-worksheet"></a>워크시트를 인쇄하려면  
  
1.  `Sheet1`의 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintOut%2A> 메서드를 호출하고, 두 복사본을 요청하고, 인쇄 전에 문서를 미리 봅니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]  
  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> 메서드를 사용 하면에서 지정된 된 개체를 표시 하는 **인쇄 미리 보기** 창. 다음 코드에서는 `Sheet1`이라는 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목이 있다고 가정합니다.  
  
#### <a name="to-preview-a-page-before-printing"></a>인쇄 전에 페이지를 미리 보려면  
  
1.  워크시트의 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]  
  
## <a name="printing-a-worksheet-in-a-vsto-add-in"></a>VSTO 추가 기능에서 워크시트 인쇄  
  
#### <a name="to-print-a-worksheet"></a>워크시트를 인쇄하려면  
  
1.  활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> 메서드를 호출하고, 두 복사본을 요청하고, 인쇄 전에 문서를 미리 봅니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]  
  
 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> 메서드를 사용 하면에서 지정된 된 개체를 표시 하는 **인쇄 미리 보기** 창.  
  
#### <a name="to-preview-a-page-before-printing"></a>인쇄 전에 페이지를 미리 보려면  
  
1.  활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트에서 맞춤법 검사](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  