---
title: "방법: 워크시트에서 프로그래밍 방식으로 데이터 정렬"
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
  - "데이터[Visual Studio에서 Office 개발], 워크시트에서 정렬"
  - "데이터 정렬, 워크시트"
  - "데이터 정렬, 워크시트"
  - "워크시트, 데이터 정렬"
ms.assetid: 2fbc6e63-02ea-4624-8d6f-bed60e06c61e
caps.latest.revision: 56
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 55
---
# 방법: 워크시트에서 프로그래밍 방식으로 데이터 정렬
  런타임에 워크시트 범위와 목록에 포함된 데이터를 정렬할 수 있습니다.  다음 코드에서는 첫 번째 열의 데이터와 두 번째 열의 데이터를 기준으로 차례로 `Fruits`라는 다중 열 범위를 정렬합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 문서 수준 사용자 지정에서 데이터 정렬  
  
#### NamedRange 컨트롤의 데이터를 정렬하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 <xref:Microsoft.Office.Tools.Excel.NamedRange.Sort%2A> 메서드를 호출합니다.  다음 예제에서는 워크시트에 `Fruits`라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 필요합니다.  이 코드는 `ThisWorkbook` 클래스가 아니라 시트 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#78](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#78)]
     [!code-vb[Trin_VstcoreExcelAutomation#78](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#78)]  
  
 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 데이터를 정렬하려면 Sheet1.vb 또는 Sheet1.cs에 다음 코드를 배치합니다.  코드에서는 `Sheet1` 워크시트에 `fruitList`라는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 있다고 가정합니다.  
  
#### ListObject 컨트롤의 데이터를 정렬하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.ListObject> 호스트 컨트롤에서 <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> 속성의 <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#79](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#79)]
     [!code-vb[Trin_VstcoreExcelAutomation#79](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#79)]  
  
## VSTO 추가 기능에서 데이터 정렬  
  
#### 기본 범위의 데이터를 정렬하려면  
  
1.  네이티브 Excel <xref:Microsoft.Office.Interop.Excel.Range> 컨트롤의 <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> 메서드를 호출합니다.  다음 예제에서는 워크시트에 `Fruits`라는 네이티브 Excel 컨트롤이 필요합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#23](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#23](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#23)]  
  
#### ListObject 컨트롤의 데이터를 정렬하려면  
  
1.  네이티브 Excel <xref:Microsoft.Office.Interop.Excel.ListObject> 컨트롤에서 <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> 속성의 <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> 메서드를 호출합니다.  다음 예제에서는 활성 워크시트에 `fruitList`라는 네이티브 Excel <xref:Microsoft.Office.Interop.Excel.ListObject> 컨트롤이 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#24](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#24](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#24)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 증분 변경되는 데이터를 사용한 범위 자동 입력](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 일정 범위에 스타일 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  