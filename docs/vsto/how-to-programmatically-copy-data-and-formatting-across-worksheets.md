---
title: "방법: 프로그래밍 방식으로 워크시트 간에 데이터 및 서식 복사 | Microsoft Docs"
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
  - "데이터 복사, Visual Studio에서 Office 개발"
  - "데이터[Visual Studio에서 Office 개발], 워크시트 간에 복사"
  - "서식 지정[Visual Studio에서 Office 개발]"
  - "워크시트, 데이터 복사"
ms.assetid: eed7dbaf-bdb5-4330-ba2e-5f3d50817eca
caps.latest.revision: 37
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 37
---
# 방법: 프로그래밍 방식으로 워크시트 간에 데이터 및 서식 복사
  <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> 메서드를 사용하면 한 시트의 범위에서 통합 문서의 다른 모든 시트로 데이터를 복사할 수 있습니다.  범위를 지정하고, 복사할 대상으로 데이터, 서식 또는 두 가지 모두를 지정합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#44)]  
  
## 코드 컴파일  
 이 예제를 사용하려면 워크시트에 `rangeData`라는 범위가 있어야 합니다.  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [방법: 프로그래밍 방식으로 선택한 셀이 포함된 워크시트 행의 서식 변경](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  