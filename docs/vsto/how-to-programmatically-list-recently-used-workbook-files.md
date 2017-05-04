---
title: "방법: 프로그래밍 방식으로 최근에 사용한 통합 문서 파일 나열 | Microsoft Docs"
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
  - "Excel[Visual Studio에서 Office 개발], 최근에 사용한 파일 나열"
  - "최근 파일 목록, Excel"
  - "RecentFiles 속성"
  - "통합 문서, 최근 사용 목록 표시"
ms.assetid: 210a3753-4845-4875-b34a-a30d3a1299b3
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# 방법: 프로그래밍 방식으로 최근에 사용한 통합 문서 파일 나열
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> 속성은 Microsoft Office Excel의 최근 사용한 파일 목록 내에 표시되는 모든 파일의 이름이 포함된 컬렉션을 반환합니다.  목록의 길이는 사용자가 유지하도록 선택한 파일의 수에 의해 결정됩니다.  그 결과를 범위에 표시할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### 최근에 사용한 통합 문서를 범위 개체에 나열하려면  
  
1.  최근 파일의 목록을 순환하여 검색하며 <xref:Microsoft.Office.Interop.Excel.Range> 개체를 기준으로 셀에 이름을 표시합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#9)]  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  