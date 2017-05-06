---
title: "방법: 프로그래밍 방식으로 워크시트 셀에 문자열 표시"
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
  - "텍스트[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "워크시트, 셀에 텍스트 표시"
ms.assetid: b19870ad-e132-49fd-994e-0a91710fa4c9
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 44
---
# 방법: 프로그래밍 방식으로 워크시트 셀에 문자열 표시
  이 예제에서는 프로그래밍 방식으로 셀에 텍스트를 표시하는 방법을 보여 줍니다.  셀에 텍스트를 표시하려면 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이나 네이티브 Excel 범위 개체를 사용합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## NamedRange 컨트롤 사용  
 이 예제에서는 `message`라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 사용합니다.  이 컨트롤은 디자인 타임에 문서 수준 사용자 지정에 추가해야 합니다.  다음 코드는 `ThisWorkbook` 클래스가 아닌 시트 클래스에 배치해야 합니다.  
  
#### NamedRange 컨트롤에 텍스트를 표시하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 값을 **Hello World**로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#68)]  
  
## 네이티브 Excel 범위 사용  
 다음 코드에서는 프로그래밍 방식으로 새 범위를 만든 다음 이 범위에 값을 할당합니다.  
  
#### Excel 범위에 텍스트를 표시하려면  
  
1.  `Sheet1`의 **A1** 셀에서 범위를 검색하고 값을 **Hello World**로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#69)]  
  
## 참고 항목  
 [연습: Windows Form을 사용하여 데이터 수집](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Office 솔루션 문제 해결](../vsto/troubleshooting-office-solutions.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  