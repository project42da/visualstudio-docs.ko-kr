---
title: "방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조 | Microsoft Docs"
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
  - "Excel[Visual Studio에서 Office 개발], 워크시트 범위 참조"
  - "범위, 참조"
  - "워크시트 범위 참조"
  - "워크시트, 범위 참조"
ms.assetid: 113633b8-426a-4d02-b6b8-d459d1f110ea
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조
  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이나 네이티브 Excel 범위 개체의 콘텐츠는 비슷한 프로세스를 사용하여 참조할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## NamedRange 컨트롤 사용  
 다음 예제에서는 워크시트에 <xref:Microsoft.Office.Tools.Excel.NamedRange>를 추가한 다음 해당 범위의 셀에 텍스트를 추가합니다.  
  
#### NamedRange 컨트롤을 참조하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 속성에 문자열을 할당합니다.  이 코드는 `ThisWorkbook` 클래스가 아닌 시트 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#46](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#46)]
     [!code-vb[Trin_VstcoreExcelAutomation#46](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#46)]  
  
## 네이티브 Excel 범위 사용  
 다음 예제에서는 워크시트에 네이티브 Excel 범위를 추가한 다음 해당 범위의 셀에 텍스트를 추가합니다.  
  
#### 네이티브 범위 개체를 참조하려면  
  
1.  범위의 <xref:Microsoft.Office.Interop.Excel.Range.Value2%2A> 속성에 문자열을 할당합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#47](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#47)]
     [!code-vb[Trin_VstcoreExcelAutomation#47](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#47)]  
  
## 참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [방법: 프로그래밍 방식으로 워크시트에서 맞춤법 검사](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 일정 범위에 스타일 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 증분 변경되는 데이터를 사용한 범위 자동 입력](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [방법: 프로그래밍 방식으로 워크시트 범위에서 텍스트 검색](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  