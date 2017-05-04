---
title: "방법: 프로그래밍 방식으로 통합 문서 열기 | Microsoft Docs"
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
  - "Excel[Visual Studio에서 Office 개발], 통합 문서 열기"
  - "통합 문서, 열기"
ms.assetid: 06c0ac87-a2c6-4cc1-87be-39be0cb81c71
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 36
---
# 방법: 프로그래밍 방식으로 통합 문서 열기
  Microsoft Office Excel의 <xref:Microsoft.Office.Interop.Excel.Workbooks> 컬렉션을 사용하면 열려 있는 모든 통합 문서에 대해 작업을 수행하거나 임의의 통합 문서를 열 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### 기존의 통합 문서를 열려면  
  
1.  통합 문서의 경로를 전달하여 <xref:Microsoft.Office.Interop.Excel.Workbooks> 컬렉션의 <xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#2)]  
  
## 코드 컴파일  
 이 코드 예제를 실행하려면 다음이 필요합니다.  
  
-   `YourWorkbook.xls`라는 통합 문서가 C 드라이브의 `Test`라는 디렉터리에 있어야 합니다.  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)   
 [방법: 프로그래밍 방식으로 새 통합 문서 만들기](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 저장](../vsto/how-to-programmatically-save-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  