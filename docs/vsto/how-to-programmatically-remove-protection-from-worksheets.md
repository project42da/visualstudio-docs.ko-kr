---
title: "방법: 프로그래밍 방식으로 워크시트의 보호 제거 | Microsoft Docs"
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
  - "워크시트, 보호 해제"
  - "문서[Visual Studio에서 Office 개발], 문서 보호"
  - "문서 보호, 워크시트에서 제거"
  - "Unprotect 메서드"
ms.assetid: 034688d2-eda7-4b4a-bcc2-d0999ff879a4
caps.latest.revision: 48
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 47
---
# 방법: 프로그래밍 방식으로 워크시트의 보호 제거
  Microsoft Office Excel 워크시트에서 프로그래밍 방식으로 보호를 제거할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 다음 예제에서는 사용자에게서 가져온 암호가 들어 있는 `getPasswordFromUser` 변수를 사용합니다.  
  
### 문서 수준 사용자 지정에서 워크시트를 보호 해제하려면  
  
1.  워크시트의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> 메서드를 호출하고 필요한 경우 암호를 전달합니다. 이 예제에서는 `Sheet1`이라는 워크시트를 사용한다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#28)]  
  
### VSTO 추가 기능의 워크시트 보호를 해제하려면  
  
1.  활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> 메서드를 호출하고 필요한 경우 암호를 전달합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#18)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서 보호](../vsto/how-to-programmatically-protect-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)  
  
  