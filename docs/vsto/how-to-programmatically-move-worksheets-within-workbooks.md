---
title: "방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트 이동 | Microsoft Docs"
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
  - "워크시트, 이동"
  - "통합 문서, 워크시트 이동"
ms.assetid: a010a633-412e-4299-9587-cacb035842c1
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트 이동
  통합 문서의 다른 워크시트를 기준으로 워크시트의 위치를 프로그래밍 방식으로 변경할 수 있습니다. 이동한 시트의 위치를 지정하지 않으면 Excel에서 이 시트가 포함된 새 통합 문서를 만듭니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### 문서 수준 사용자 지정에서 워크시트를 이동하려면  
  
1.  통합 문서에 있는 총 시트 수를 변수에 할당하고 첫 번째 워크시트가 마지막 워크시트가 되도록 이동합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#24](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#24)]  
  
### VSTO 추가 기능에서 워크시트를 이동하려면  
  
1.  통합 문서에 있는 총 시트 수를 변수에 할당하고 첫 번째 워크시트가 마지막 워크시트가 되도록 이동합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#16)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)  
  
  