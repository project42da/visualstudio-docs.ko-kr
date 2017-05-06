---
title: "방법: 프로그래밍 방식으로 통합 문서 보호"
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
  - "문서 보호, 통합 문서에 추가"
  - "문서 보호, 통합 문서에서 제거"
  - "문서[Visual Studio에서 Office 개발], 문서 보호"
  - "통합 문서, 암호"
  - "통합 문서, 보호"
  - "통합 문서, 보호 해제"
ms.assetid: 553c67b9-e2a4-46b6-878c-5b4b4efa4589
caps.latest.revision: 43
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# 방법: 프로그래밍 방식으로 통합 문서 보호
  사용자가 워크시트를 추가 또는 삭제하지 못하도록 Microsoft Office Excel 통합 문서를 보호하거나 프로그래밍 방식으로 통합 문서의 보호를 해제할 수도 있습니다.  선택적으로 암호를 지정할 수 있고 사용자가 시트를 옮기지 못하도록 통합 문서의 구조를 보호할지 여부 및 통합 문서의 창을 보호할지 여부를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 통합 문서를 보호해도 사용자는 계속하여 셀을 편집할 수 있습니다.  데이터를 보호하려면 워크시트를 보호해야 합니다.  자세한 내용은 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)을 참조하십시오.  
  
 다음 코드 예제에서는 사용자로부터 제공받은 암호가 포함된 변수를 사용합니다.  
  
## 문서 수준 사용자 지정의 일부인 통합 문서 보호  
  
#### 통합 문서를 보호하려면  
  
1.  통합 문서의 <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> 메서드를 호출하고 암호를 지정합니다.  다음 코드 예제를 사용하려면 시트 클래스가 아닌 `ThisWorkbook` 클래스에서 이 코드 예제를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/ThisWorkbook.vb#10)]  
  
#### 통합 문서 보호를 해제하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> 메서드를 호출하고 필요한 경우 암호를 전달합니다.  다음 코드 예제를 사용하려면 시트 클래스가 아닌 `ThisWorkbook` 클래스에서 이 코드 예제를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/ThisWorkbook.vb#11)]  
  
## 응용 프로그램 수준 추가 기능을 사용하여 통합 문서 보호  
  
#### 통합 문서를 보호하려면  
  
1.  통합 문서의 <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> 메서드를 호출하고 암호를 지정합니다.  이 코드 예제에서는 활성 통합 문서를 사용합니다.  이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#6)]  
  
#### 통합 문서 보호를 해제하려면  
  
1.  활성 통합 문서의 <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> 메서드를 호출하고 필요한 경우 암호를 전달합니다.  이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#7)]  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  