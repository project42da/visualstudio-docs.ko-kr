---
title: "방법: 프로그래밍 방식으로 워크시트에서 행 그룹화"
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
  - "열[Visual Studio에서 Office 개발], 그룹 해제"
  - "그룹"
  - "그룹[Visual Studio에서 Office 개발], 워크시트에서 지우기"
  - "그룹, 워크시트에서 만들기"
  - "범위, 그룹 만들기"
  - "행[Visual Studio에서 Office 개발], 그룹 해제"
  - "워크시트, 그룹 지우기"
  - "워크시트, 그룹 만들기"
  - "워크시트, 행 및 열 그룹 해제"
ms.assetid: 48037dca-35a2-4df2-918b-6a9f568fae91
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 45
---
# 방법: 프로그래밍 방식으로 워크시트에서 행 그룹화
  하나 이상의 전체 행을 그룹화할 수 있습니다.  워크시트에서 그룹을 만들려면 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이나 네이티브 Excel 범위 개체를 사용합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## NamedRange 컨트롤 사용  
 디자인 타임에 문서 수준 프로젝트에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 추가한 경우 해당 컨트롤을 사용하여 프로그래밍 방식으로 그룹을 만들 수 있습니다.  다음 예제에서는 `data2001`, `data2002` 및 `dataAll`이라는 세 개의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 동일한 워크시트에 있는 것으로 가정합니다.  명명된 각 범위는 워크시트의 전체 행을 참조합니다.  
  
#### 워크시트에서 NamedRange 컨트롤의 그룹을 만들려면  
  
1.  각 범위의 <xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A> 메서드를 호출하여 세 개의 명명된 범위를 그룹화합니다.  이 코드는 `ThisWorkbook` 클래스가 아닌 시트 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  행 그룹을 해제하려면 <xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A> 메서드를 호출합니다.  
  
## 네이티브 Excel 범위 사용  
 이 코드에서는 `data2001`, `data2002` 및 `dataAll`이라는 세 개의 Excel 범위가 워크시트에 있는 것으로 가정합니다.  
  
#### 워크시트에서 Excel 범위의 그룹을 만들려면  
  
1.  각 범위의 <xref:Microsoft.Office.Interop.Excel.Range.Group%2A> 메서드를 호출하여 세 개의 명명된 범위를 그룹화합니다.  다음 예제에서는 `data2001`, `data2002` 및 `dataAll`이라는 세 개의 <xref:Microsoft.Office.Interop.Excel.Range> 컨트롤이 동일한 워크시트에 있는 것으로 가정합니다.  명명된 각 범위는 워크시트의 전체 행을 참조합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  행 그룹을 해제하려면 <xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A> 메서드를 호출합니다.  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: 워크시트에 NamedRange 컨트롤 추가](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  