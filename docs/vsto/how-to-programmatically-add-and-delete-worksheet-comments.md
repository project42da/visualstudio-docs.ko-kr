---
title: "방법: 프로그래밍 방식으로 워크시트 메모 추가 및 삭제"
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
  - "범위, 메모"
  - "워크시트, 메모"
  - "메모, 워크시트"
ms.assetid: 3408ce22-a7b7-4e2b-bfc1-dc24d679ee73
caps.latest.revision: 53
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 52
---
# 방법: 프로그래밍 방식으로 워크시트 메모 추가 및 삭제
  프로그래밍 방식으로 Microsoft Office Excel 워크시트에서 메모를 추가하거나 삭제할 수 있습니다. 메모는 다중 셀 범위가 아닌 단일 셀에만 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 문서 수준 프로젝트에서 메모 추가 및 삭제  
 다음 예제에서는 `dateComment`라는 단일 셀 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 `Sheet1`이라는 워크시트에 있다고 가정합니다.  
  
#### 명명된 범위에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> 메서드를 호출하고 메모 텍스트를 제공합니다. 이 코드는 `Sheet1` 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#30](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#30)]  
  
#### 명명된 범위에서 메모를 삭제하려면  
  
1.  메모가 해당 범위에 있는지 확인하고 삭제합니다. 이 코드는 `Sheet1` 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#29](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#29)]  
  
## VSTO 추가 기능 프로젝트에서 메모 추가 및 삭제  
 다음 예제에서는 `dateComment`라는 단일 셀 <xref:Microsoft.Office.Interop.Excel.Range>가 활성 워크시트에 있다고 가정합니다.  
  
#### Excel 범위에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Range>의 <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> 메서드를 호출하여 메모 텍스트를 제공합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#20)]  
  
#### Excel 범위에서 메모를 삭제하려면  
  
1.  메모가 해당 범위에 있는지 확인하고 삭제합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#19)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 메모 표시](../vsto/how-to-programmatically-display-worksheet-comments.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)  
  
  