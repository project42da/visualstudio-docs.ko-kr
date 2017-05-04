---
title: "방법: 프로그래밍 방식으로 Excel 범위에서 날짜 값 저장 및 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "날짜 값"
  - "날짜 값, Excel 범위에서 저장"
  - "날짜, Excel 범위에서 검색"
  - "날짜, Excel 범위에서 저장"
  - "Excel[Visual Studio에서 Office 개발], 범위에서 날짜 값 검색"
  - "Excel[Visual Studio에서 Office 개발], 범위에서 날짜 값 저장"
  - "범위, 날짜 값 검색"
  - "범위, 날짜 값 저장"
ms.assetid: e1cdd262-0356-4499-8bc5-e730f74235a2
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# 방법: 프로그래밍 방식으로 Excel 범위에서 날짜 값 저장 및 검색
  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이나 네이티브 Excel 범위 개체에 값을 저장하고 검색할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 1900년 1월 1일 또는 그 이후를 나타내는 날짜 값을 Visual Studio의 Office 개발 도구를 사용하여 범위에 저장하는 경우 날짜 값은 OA\(OLE 자동화\) 형식으로 저장됩니다.  OA\(OLE 자동화\) 형식의 날짜 값을 검색하려면 <xref:System.DateTime.FromOADate%2A> 메서드를 사용해야 합니다.  1900년 1월 1일 이전의 날짜는 문자열로 저장됩니다.  
  
> [!NOTE]  
>  1900년 1월과 2월의 경우에는 Excel 날짜가 OA 날짜와 다릅니다.  **1904 날짜 체계** 옵션이 선택된 경우에도 차이가 발생합니다.  코드 예제에서는 이러한 차이를 제대로 처리하지 않습니다.  
  
## NamedRange 컨트롤 사용  
  
-   이 예제는 문서 수준 사용자 지정을 위한 것입니다.  다음 코드는 `ThisWorkbook` 클래스가 아닌 시트 클래스에 배치해야 합니다.  
  
#### 명명된 범위에 날짜 값을 저장하려면  
  
1.  **A1** 셀에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 만듭니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#50](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#50)]  
  
2.  `NamedRange1`의 값으로 오늘 날짜를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#51](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#51)]  
  
#### 명명된 범위에서 날짜 값을 검색하려면  
  
1.  `NamedRange1`에서 날짜 값을 검색합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#52](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#52)]  
  
## 네이티브 Excel 범위 사용  
  
#### 네이티브 Excel 범위 개체에 날짜 값을 저장하려면  
  
1.  **A1** 셀을 나타내는 <xref:Microsoft.Office.Interop.Excel.Range>를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#25)]  
  
2.  `rng`의 값으로 오늘 날짜를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#26)]  
  
#### 네이티브 Excel 범위 개체에서 날짜 값을 검색하려면  
  
1.  `rng`에서 날짜 값을 검색합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#27)]  
  
## 참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [Excel 개체 모델 개요](../vsto/excel-object-model-overview.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  