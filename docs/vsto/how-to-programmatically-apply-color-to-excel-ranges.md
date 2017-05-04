---
title: "방법: 프로그래밍 방식으로 Excel 범위에 색 적용 | Microsoft Docs"
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
  - "색, Excel 범위"
  - "서식 지정[Visual Studio에서 Office 개발]"
  - "범위, 색 적용"
ms.assetid: a9c40229-5308-459a-9216-7e13d82c7cb5
caps.latest.revision: 47
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: 프로그래밍 방식으로 Excel 범위에 색 적용
  셀 범위 내의 텍스트에 색을 적용하려면 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이나 네이티브 Excel 범위 개체를 사용합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## NamedRange 컨트롤 사용  
 이 예제는 문서 수준 사용자 지정을 위한 것입니다.  
  
#### NamedRange 컨트롤에 색을 적용하려면  
  
1.  A1 셀에서 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 만듭니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#65](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#65)]
     [!code-vb[Trin_VstcoreExcelAutomation#65](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#65)]  
  
2.  <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤에서 텍스트의 색을 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#66](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#66)]
     [!code-vb[Trin_VstcoreExcelAutomation#66](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#66)]  
  
## 네이티브 Excel 범위 사용  
  
#### 네이티브 Excel 범위 개체에 색을 적용하려면  
  
1.  A1 셀에 범위를 만든 다음 텍스트 색을 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#67](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#67)]
     [!code-vb[Trin_VstcoreExcelAutomation#67](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#67)]  
  
## 참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 일정 범위에 스타일 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  