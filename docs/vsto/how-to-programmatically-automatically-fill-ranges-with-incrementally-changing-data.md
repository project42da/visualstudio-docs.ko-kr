---
title: "방법: 증분 변경 되는 데이터를 사용한 프로그래밍 방식으로 자동으로 채우기 범위 | Microsoft Docs"
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
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
ms.assetid: 27639d55-8ab5-483c-8907-2ea50dfd2188
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4fad536f7e9f0891f7630cd86d31cea279d5706f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>방법: 프로그래밍 방식으로 증분 변경되는 데이터를 사용한 범위 자동 입력
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Excel.Range> 개체를 사용 하면 값이 포함 된 워크시트의 범위를 자동으로 채울 수 있습니다. 대부분의 경우는 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 증분적으로 증가 하거나 감소 하는 값 범위에 저장할 메서드를 사용 합니다. 옵션 상수를 제공 하 여 동작을 지정할 수는 <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> 열거형입니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 사용 하는 경우에 두 범위를 지정 해야 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   호출 하는 범위는 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드를 채우기의 시작 위치를 지정 하 고 초기 값을 포함 합니다.  
  
-   에 대 한 매개 변수로 전달 된 범위를 채우기는 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드. 이 대상 범위는 초기 값을 포함 하는 범위를 포함 해야 합니다.  
  
    > [!NOTE]  
    >  전달할 수 없습니다는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 대신는 <xref:Microsoft.Office.Interop.Excel.Range>합니다. 자세한 내용은 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 채울 범위의 첫 번째 셀에는 초기 값이 있어야 합니다.  
  
 이 예제에서는 3 개의 영역을 채워야 합니다.  
  
-   B 열 5 평일을 포함 하는 것입니다. 초기 값을 입력 **월요일** B1 셀에 있습니다.  
  
-   열 C 5 개월이 포함 하는 것입니다. 초기 값을 입력 **년 1 월** C1 셀에서입니다.  
  
-   열 D는 일련의 각 행 마다 2 씩 증가 숫자를 포함 하는 것입니다. 초기 값에 대 한 입력 **4** D1 셀에서 및 **6** D2 셀에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 범위에 스타일을 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 Excel 계산 실행](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  