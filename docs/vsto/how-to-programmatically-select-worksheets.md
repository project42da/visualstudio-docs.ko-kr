---
title: "방법: 프로그래밍 방식으로 워크시트 선택 | Microsoft Docs"
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
- worksheets, selecting
- Excel projects, selecting worksheets
ms.assetid: 9e7cdb11-e825-4c9f-abcd-d46fd20dc5e0
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dd84ad38955620ad09ab9fab5fc178241e682948
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-select-worksheets"></a>방법: 프로그래밍 방식으로 워크시트 선택
  <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A> 메서드는 사용자의 선택 영역을 새 개체로 이동하는 지정된 개체를 선택합니다. 사용자의 선택 영역을 변경하지 않고 포커스를 개체로 가져오려는 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet.Activate%2A> 메서드를 사용합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 VSTO 추가 기능에서 기존 워크시트를 선택하려는 경우 또는 워크시트가 런타임에 문서 수준 사용자 지정에서 생성된 경우 Excel 통합 문서의 Excel <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션을 사용하여 액세스해야 합니다. 그렇지 않은 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목에 직접 액세스할 수 있습니다.  
  
## <a name="using-the-worksheet-host-item"></a>워크시트 호스트 항목 사용  
 문서 수준 사용자 지정에서 다음 코드를 추가 **Sheet1.vb** 또는 **Sheet1.cs**합니다.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-a-host-item"></a>호스트 항목을 사용하여 통합 문서의 첫 번째 워크시트를 선택하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A>의 `Sheet1` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#19)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Excel 통합 문서의 시트 컬렉션 사용  
 Excel <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션을 사용하여 워크시트에 액세스합니다.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-the-sheets-collection-of-the-excel-workbook"></a>Excel 통합 문서의 시트 컬렉션을 사용하여 통합 문서의 첫 번째 워크시트를 선택하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션의 <xref:Microsoft.Office.Interop.Excel.Sheets.Select%2A> 메서드를 호출하여 활성 통합 문서의 첫 번째 워크시트를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#20)]  
  
## <a name="see-also"></a>참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 인쇄](../vsto/how-to-programmatically-print-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  