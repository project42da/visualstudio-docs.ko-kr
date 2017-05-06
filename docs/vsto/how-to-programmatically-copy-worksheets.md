---
title: "방법: 프로그래밍 방식으로 워크시트 복사"
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
  - "Excel[Visual Studio에서 Office 개발], 워크시트 복사"
  - "워크시트, 복사"
ms.assetid: e49e03f5-7b2f-416b-b5fe-0965336c47e1
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 30
---
# 방법: 프로그래밍 방식으로 워크시트 복사
  워크시트의 복사본을 만들고 통합 문서의 기존 워크시트 앞이나 뒤에 해당 워크시트를 삽입할 수 있습니다.  워크시트를 삽입할 위치를 지정하지 않으면 새 워크시트를 포함할 새 통합 문서가 생성됩니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  프로그래밍 방식으로 워크시트를 복사하든 또는 최종 사용자가 수동으로 워크시트를 복사하든 관계없이 새 워크시트에는 숨겨진 코드가 없으며 새 워크시트의 컨트롤이 작동하지 않습니다.  이는 새로 복사한 워크시트가 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목이 아니라 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체이기 때문입니다.  Windows Forms 컨트롤 및 호스트 컨트롤은 호스트 항목에만 추가할 수 있습니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하세요.  
  
### 문서 수준 사용자 지정에서 통합 문서에 복사된 워크시트를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> 메서드를 사용하여 현재 통합 문서의 첫 번째 워크시트를 복사하고 세 번째 시트 뒤에 복사본을 배치합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomation#16](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#16)]  
  
### VSTO 추가 기능에서 통합 문서에 복사된 워크시트를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> 메서드를 사용하여 현재 통합 문서의 첫 번째 워크시트를 복사하고 세 번째 시트 뒤에 복사본을 배치합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#12)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 선택](../vsto/how-to-programmatically-select-worksheets.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  