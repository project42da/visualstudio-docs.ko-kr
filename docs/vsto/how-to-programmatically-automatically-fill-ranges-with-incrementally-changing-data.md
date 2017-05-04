---
title: "방법: 프로그래밍 방식으로 증분 변경되는 데이터를 사용한 범위 자동 입력 | Microsoft Docs"
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
  - "Autofill 메서드[Excel]"
  - "자동으로 범위 채우기"
  - "범위, 자동으로 채우기"
  - "통합 문서, 범위 채우기"
ms.assetid: 27639d55-8ab5-483c-8907-2ea50dfd2188
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 방법: 프로그래밍 방식으로 증분 변경되는 데이터를 사용한 범위 자동 입력
  <xref:Microsoft.Office.Interop.Excel.Range> 개체의 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드를 사용하면 값을 사용하여 자동으로 워크시트의 범위를 채울 수 있습니다.  대부분의 경우 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드는 증분적으로 증가하거나 감소하는 값을 범위에 저장하는 데 사용됩니다.  <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> 열거형의 상수를 선택적으로 제공하여 동작을 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>을 사용할 때는 두 개의 범위를 지정해야 합니다.  
  
-   <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드를 호출하는 범위. 이 범위는 채울 시작 지점을 지정하고 초기 값을 포함합니다.  
  
-   채워야 할 범위. 이 범위는 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드에 매개 변수로 전달됩니다.  이 대상 범위에는 초기 값이 포함된 범위가 들어 있어야 합니다.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Interop.Excel.Range> 대신 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 전달할 수 없습니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하십시오.  
  
## 예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#49)]  
  
## 코드 컴파일  
 채우려는 범위의 첫 번째 셀에는 초기 값이 포함되어야 합니다.  
  
 이 예제에서는 세 가지 영역을 채워야 합니다.  
  
-   B 열에는 요일을 나타내는 다섯 개의 단어를 입력합니다.  초기 값으로 B1 셀에 **Monday**를 입력합니다.  
  
-   C 열에는 달을 나타내는 다섯 개의 단어를 입력합니다.  초기 값으로 C1 셀에 **January**를 입력합니다.  
  
-   D 열에는 각 행마다 2씩 증가하는 일련의 숫자를 입력합니다.  초기 값으로 D1 셀에 **4**를 입력하고 D2 셀에 **6**을 입력합니다.  
  
## 참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 일정 범위에 스타일 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 Excel 계산 실행](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  