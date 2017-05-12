---
title: "방법: 프로그래밍 방식으로 통합 문서의 모든 워크시트 나열"
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
  - "통합 문서, 워크시트 목록 표시"
  - "워크시트, 목록 표시"
ms.assetid: 38b63d1d-6047-44e8-b089-c576c6179e4a
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 45
---
# 방법: 프로그래밍 방식으로 통합 문서의 모든 워크시트 나열
  <xref:Microsoft.Office.Interop.Excel.Workbook> 클래스는 <xref:Microsoft.Office.Interop.Excel.Worksheets> 개체를 제공합니다.  이 개체에는 통합 문서에 있는 모든 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체의 컬렉션이 들어 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### 문서 수준 사용자 지정의 통합 문서에 있는 기존 워크시트를 모두 나열하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets> 컬렉션을 순환하면서 각 시트의 이름을 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤에서 오프셋된 셀에 전달합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#21](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomation#21](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#21)]  
  
### VSTO 추가 기능의 통합 문서에 있는 기존 워크시트를 모두 나열하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets> 컬렉션을 반복하면서 각 시트의 이름을 <xref:Microsoft.Office.Interop.Excel.Range> 개체에서 오프셋된 셀에 전달합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#13)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트 이동](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)  
  
  