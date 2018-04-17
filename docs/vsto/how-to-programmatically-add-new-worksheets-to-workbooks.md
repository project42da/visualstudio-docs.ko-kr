---
title: '방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, adding worksheets
- workbooks, creating worksheets
- worksheets, creating
- worksheets, adding to workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 934b3cb9b333c1cd9c551346eb7ac30edcd5e368
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-add-new-worksheets-to-workbooks"></a>방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가
  프로그래밍 방식으로 워크시트를 만든 다음 통합 문서의 워크시트 컬렉션에 워크시트를 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-add-a-new-worksheet-to-a-workbook-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 통합 문서에 새 워크시트를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> 컬렉션의 <xref:Microsoft.Office.Interop.Excel.Sheets> 메서드를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#15)]  
  
     새 워크시트는 네이티브 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체이고 호스트 항목이 아닙니다. <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 추가하려는 경우 디자인 타임에 워크시트를 추가해야 합니다.  
  
### <a name="to-add-a-new-worksheet-to-a-workbook-in-a-vsto-add-in"></a>VSTO 추가 기능에서 통합 문서에 새 워크시트를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> 컬렉션의 <xref:Microsoft.Office.Interop.Excel.Sheets> 메서드를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#11)]  
  
     새 워크시트는 네이티브 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체이고 호스트 항목이 아닙니다. 네이티브 <xref:Microsoft.Office.Tools.Excel.Worksheet> 개체에서 <xref:Microsoft.Office.Interop.Excel.Worksheet> 호스트 항목을 생성할 수도 있습니다. 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 선택](../vsto/how-to-programmatically-select-worksheets.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  