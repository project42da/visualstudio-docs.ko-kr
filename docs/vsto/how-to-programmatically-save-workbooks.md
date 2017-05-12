---
title: "방법: 프로그래밍 방식으로 통합 문서 저장"
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
  - "통합 문서, 저장"
  - "통합 문서, 백업 복사본 저장"
  - "통합 문서, XML 형식으로 저장"
ms.assetid: 991ccf9b-5213-4094-9030-284ec167bdcc
caps.latest.revision: 50
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 49
---
# 방법: 프로그래밍 방식으로 통합 문서 저장
  통합 문서를 저장하는 방법에는 여러 가지가 있습니다.  경로를 변경하지 않고 통합 문서를 저장할 수 있습니다.  통합 문서가 이전에 저장되지 않은 경우 경로를 지정하여 통합 문서를 저장해야 합니다.  명시적 경로 없이 Microsoft Office Excel은 파일을 만들 때 지정된 이름으로 현재 폴더에 파일을 저장합니다.  메모리에 열려 있는 통합 문서를 수정하지 않고 통합 문서의 복사본을 저장할 수도 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 경로를 변경하지 않고 통합 문서 저장  
  
#### 문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  ThisWorkbook 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/ThisWorkbook.vb#4)]  
  
#### VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> 메서드를 호출하여 활성 통합 문서를 저장합니다.  다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#3)]  
  
## 새 경로를 사용하여 통합 문서 저장  
 필요에 따라 파일 형식, 암호, 액세스 모드 등을 지정하여 지정된 통합 문서를 새 위치나 새 이름으로 저장할 수 있습니다.  
  
> [!NOTE]  
>  일부 형식으로 저장하려면 조작이 필요하기 때문에 새 경로를 사용하여 통합 문서를 저장하기 전에 <xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A> 속성을 **False**로 설정할 수도 있습니다.  이 속성을 **False**로 설정하면 Excel에서 모든 기본값을 사용합니다.  
  
#### 문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> 메서드를 호출합니다.  다음 코드 예제를 사용하려면 `ThisWorkbook` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/ThisWorkbook.vb#5)]  
  
#### VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> 메서드를 호출하여 활성 통합 문서를 새 경로에 저장합니다.  다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#4)]  
  
## 통합 문서의 복사본 저장  
 메모리에 열려 있는 통합 문서를 수정하지 않고 통합 문서의 복사본을 파일에 저장할 수 있습니다.  이 기능은 통합 문서의 위치를 수정하지 않고 백업 복사본을 만들려는 경우에 유용합니다.  
  
#### 문서 수준 사용자 지정과 연결된 통합 문서를 저장하려면  
  
1.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> 메서드를 호출합니다.  다음 코드 예제를 사용하려면 `ThisWorkbook` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/ThisWorkbook.vb#6)]  
  
#### VSTO 추가 기능에서 활성 통합 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> 메서드를 호출하여 활성 통합 문서의 복사본을 저장합니다.  다음 코드 예제를 사용하려면 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/CS/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomationAddIn/VB/ThisAddIn.vb#5)]  
  
## 강력한 프로그래밍  
 통합 문서를 저장하거나 복사하는 메서드를 대화형으로 취소하면 코드에서 런타임 오류가 발생합니다.  예를 들어 프로시저에서 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> 메서드를 호출하지만 Excel에서 메시지가 표시되지 않도록 설정하는 경우 메시지가 표시될 때 사용자가 **취소**를 클릭하면 Excel에서 런타임 오류가 발생합니다.  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  