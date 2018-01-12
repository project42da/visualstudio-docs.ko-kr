---
title: "방법: 프로그래밍 방식으로 Excel 계산 실행 | Microsoft Docs"
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
- ranges, running calculations
- calculations, running in Excel
- Excel [Office development in Visual Studio], running calculations programmatically
- workbooks, running calculations
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d1b18b9de3c79385885c23fdbf0cac99a14c3e27
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-run-excel-calculations"></a>방법: 프로그래밍 방식으로 Excel 계산 실행  
  비슷한 프로세스를 사용 하 여 계산을 실행 하는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 또는 네이티브 Excel 범위 개체입니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="running-calculations-in-a-namedrange-control"></a>NamedRange 컨트롤의 계산 실행  
 다음 예제에서는 한 <xref:Microsoft.Office.Tools.Excel.NamedRange> A1 셀에 셀을 계산 됩니다. 이 코드는 `ThisWorkbook` 클래스가 아니라 시트 클래스에 배치해야 합니다.  
  
#### <a name="to-run-calculations-in-a-namedrange-control"></a>NamedRange 컨트롤에서 계산을 실행 하려면  
  
1.  명명된 된 범위를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#75)]
     [!code-vb[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#75)]  
  
2.  호출 된 <xref:Microsoft.Office.Tools.Excel.NamedRange.Calculate%2A> 지정 된 범위의 메서드.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#76)]
     [!code-vb[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#76)]  
  
## <a name="running-calculations-in-a-native-excel-range"></a>네이티브 Excel 범위에서 계산 실행  
  
#### <a name="to-run-calculations-in-a-native-excel-range"></a>네이티브 Excel 범위에서 계산을 실행 하려면  
  
1.  명명된 된 범위를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#30)]  
  
2.  호출 된 <xref:Microsoft.Office.Interop.Excel.Range.Calculate%2A> 지정 된 범위의 메서드.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#31)]  
  
## <a name="see-also"></a>참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  