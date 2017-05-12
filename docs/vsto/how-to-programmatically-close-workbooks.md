---
title: "방법: 프로그래밍 방식으로 통합 문서 닫기"
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
  - "통합 문서, 닫기"
  - "Excel[Visual Studio에서 Office 개발], 통합 문서 닫기"
ms.assetid: 50709caf-2ad8-4843-987c-9a34c8c1e4fe
caps.latest.revision: 52
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 51
---
# 방법: 프로그래밍 방식으로 통합 문서 닫기
  활성 통합 문서를 닫거나 닫을 통합 문서를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 활성 통합 문서 닫기  
 활성 통합 문서를 닫는 절차에는 문서 수준 사용자 지정 및 VSTO 추가 기능에 대해 각각 하나씩, 두 가지가 있습니다.  
  
#### 문서 수준 사용자 지정에서 활성 통합 문서를 닫으려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> 메서드를 호출하여 사용자 지정과 연결된 통합 문서를 닫습니다. 다음 코드 예제를 사용하려면 Excel용 문서 수준 프로젝트의 `Sheet1` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#3)]  
  
#### VSTO 추가 기능에서 활성 통합 문서를 닫으려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> 메서드를 호출하여 활성 통합 문서를 닫습니다. 다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#1)]  
  
## 이름으로 지정한 통합 문서 닫기  
 이름으로 지정한 통합 문서를 닫는 방법은 VSTO 추가 기능과 문서 수준 사용자 지정에서 동일합니다.  
  
#### 이름으로 지정한 통합 문서를 닫으려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Workbooks> 컬렉션에 대한 인수로 통합 문서 이름을 지정합니다. 다음 코드 예제에서는 **NewWorkbook**이라는 통합 문서가 Excel에서 열려 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#2)]  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 저장](../vsto/how-to-programmatically-save-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 열기](../vsto/how-to-programmatically-open-workbooks.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  