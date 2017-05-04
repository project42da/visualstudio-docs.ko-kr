---
title: "방법: 프로그래밍 방식으로 워크시트 숨기기 | Microsoft Docs"
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
  - "숨겨진 워크시트"
  - "워크시트, 숨기기"
ms.assetid: 3208f633-137f-47f9-9c9c-2cf8e3c72096
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: 프로그래밍 방식으로 워크시트 숨기기
  통합 문서의 모든 워크시트를 표시하거나 숨길 수 있습니다. 워크시트를 숨기려면 워크시트 호스트 항목을 사용하거나 통합 문서의 시트 컬렉션을 통해 워크시트에 액세스합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 워크시트 호스트 항목 사용  
 문서 수준 사용자 지정에서 디자인 타임에 워크시트가 추가된 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> 속성을 사용하여 지정된 워크시트를 숨깁니다.  
  
#### 워크시트 호스트 항목을 사용하여 워크시트를 숨기려면  
  
1.  `Sheet1` 호스트 항목의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> 속성을 <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> 열거형 값으로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#25)]  
  
## Excel 통합 문서의 시트 컬렉션 사용  
 다음과 같은 경우 Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션을 통해 워크시트에 액세스합니다.  
  
-   VSTO 추가 기능에서 워크시트를 숨기려고 합니다.  
  
-   숨기려는 워크시트는 문서 수준 사용자 지정에서 런타임에 생성되었습니다.  
  
#### Excel 통합 문서의 시트 컬렉션을 사용하여 워크시트를 숨기려면  
  
1.  워크시트의 <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> 속성을 <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> 열거형 값으로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#26)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트 이동](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)  
  
  