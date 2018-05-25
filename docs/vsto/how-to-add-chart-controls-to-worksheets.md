---
title: '방법: 워크시트에 Chart 컨트롤 추가'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 05fc2cafda3ed4aa0ff7756062c1cec0429ebc96
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-add-chart-controls-to-worksheets"></a>방법: 워크시트에 Chart 컨트롤 추가
  추가할 수 있습니다 <xref:Microsoft.Office.Tools.Excel.Chart> 디자인 타임 및 런타임에 문서 수준 사용자 지정에서 Microsoft Office Excel 워크시트에 컨트롤입니다. 추가할 수도 있습니다 <xref:Microsoft.Office.Tools.Excel.Chart> VSTO 추가 기능에서 런타임에 컨트롤입니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 차트 컨트롤 추가](#designtime)  
  
-   [문서 수준 프로젝트에서 런타임에 Chart 컨트롤 추가](#runtimedoclevel)  
  
-   [VSTO 추가 기능 프로젝트에서 런타임에 Chart 컨트롤 추가](#runtimeaddin)  
  
 에 대 한 자세한 내용은 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤 참조 [차트 컨트롤](../vsto/chart-control.md)합니다.  
  
##  <a name="designtime"></a> 디자인 타임에 차트 컨트롤 추가  
 응용 프로그램 내에서 차트를 추가하는 것과 동일한 방식으로 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 워크시트에 추가할 수 있습니다.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤에서 지원 하지 않는 **도구 상자** 또는 **데이터 소스** 창.  
  
### <a name="to-add-a-chart-host-control-to-a-worksheet-in-excel"></a>Excel의 워크시트에 차트 호스트 컨트롤을 추가하려면  
  
1.  에 **삽입** 탭에 **차트** 그룹에서 클릭 **열**, 차트의 범주를 클릭 한 다음 원하는 차트 종류를 클릭 합니다.  
  
2.  에 **차트 삽입** 대화 상자를 클릭 **확인**합니다.  
  
3.  에 **디자인** 탭에 **데이터** 그룹에서 클릭 **데이터 선택**합니다.  
  
4.  에 **데이터 원본 선택** 대화 상자에서를 클릭 하 고 **차트** **데이터 범위** 상자 하 고 기본 선택 값을 지웁니다.  
  
5.  에 **차트에 대 한 데이터** 시트 스타일은 차트에 대 한 데이터가 포함 된 셀 범위를 선택 합니다 (셀 **A5** 통해 **D8**).  
  
6.  에 **데이터 원본 선택** 대화 상자를 클릭 **확인**합니다.  
  
##  <a name="runtimedoclevel"></a> 문서 수준 프로젝트에서 런타임에 chart 컨트롤 추가  
 추가할 수는 <xref:Microsoft.Office.Tools.Excel.Chart> 런타임에 동적으로 제어 합니다. 동적으로 생성된 차트는 문서를 닫을 때 문서에 호스트 컨트롤로 유지되지 않습니다. 자세한 내용은 참조 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.  
  
#### <a name="to-add-a-chart-control-to-a-worksheet-programmatically"></a>프로그래밍 방식으로 워크시트에 차트 컨트롤을 추가하려면  
  
1.  `Sheet1`의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트 처리기에서 다음 코드를 삽입하여 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#1)]  
  
##  <a name="runtimeaddin"></a> VSTO 추가 기능 프로젝트에서 런타임에 chart 컨트롤 추가  
 VSTO 추가 기능 프로젝트에서 열려 있는 워크시트에 프로그래밍 방식으로 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [확장 Word 문서 및 Excel VSTO 추가 기능에서 런타임에 통합](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)합니다.  
  
 동적으로 생성된 차트 컨트롤은 워크시트를 닫을 때 워크시트에서 호스트 컨트롤로 유지되지 않습니다. 자세한 내용은 참조 [런타임에서 문서를 Office에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.  
  
#### <a name="to-add-a-chart-control-to-a-worksheet-programmatically"></a>프로그래밍 방식으로 워크시트에 차트 컨트롤을 추가하려면  
  
1.  다음 코드는 열려 있는 워크시트를 기반으로 하는 워크시트 호스트 항목을 생성하고 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#9](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#9)]
     [!code-vb[Trin_Excel_Dynamic_Controls#9](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#9)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 예제에는 다음과 같은 요구 사항이 있습니다.  
  
-   워크시트의 A5부터 D8까지의 범위에 저장된 차트로 작성할 데이터  
  
## <a name="see-also"></a>참고자료  
 [Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [차트 컨트롤](../vsto/chart-control.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  