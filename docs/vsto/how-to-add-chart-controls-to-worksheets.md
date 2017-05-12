---
title: "방법: 워크시트에 Chart 컨트롤 추가"
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
  - "차트 컨트롤[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "컨트롤[Visual Studio에서 Office 개발], 워크시트에 추가"
ms.assetid: f02568e7-5caa-45b4-aa2a-4f73b0565d4e
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# 방법: 워크시트에 Chart 컨트롤 추가
  디자인 타임 및 런타임에 문서 수준 사용자 지정에서 Microsoft Office Excel 워크시트에 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가할 수 있습니다.  런타임에 VSTO 추가 기능에서 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가할 수도 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 차트 컨트롤 추가](#designtime)  
  
-   [런타임에 문서 수준 프로젝트에서 차트 컨트롤 추가](#runtimedoclevel)  
  
-   [런타임에 VSTO 추가 기능 프로젝트에서 차트 컨트롤 추가](#runtimeaddin)  
  
 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤에 대한 자세한 내용은 [Chart 컨트롤](../vsto/chart-control.md)을 참조하세요.  
  
##  <a name="designtime"></a> 디자인 타임에 차트 컨트롤 추가  
 응용 프로그램 내에서 차트를 추가하는 것과 동일한 방식으로 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 워크시트에 추가할 수 있습니다.  
  
> [!NOTE]  
>  **도구 상자** 또는 **데이터 소스** 창에서는 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 사용할 수 없습니다.  
  
#### Excel의 워크시트에 차트 호스트 컨트롤을 추가하려면  
  
1.  **삽입** 탭의 **차트** 그룹에서 **열**을 클릭하고 차트 범주를 클릭한 다음 원하는 차트 종류를 클릭합니다.  
  
2.  **차트 삽입** 대화 상자에서 **확인**을 클릭합니다.  
  
3.  **디자인** 탭의 **데이터** 그룹에서 **데이터 선택**을 클릭합니다.  
  
4.  **데이터 소스 선택** 대화 상자에서 **차트데이터 범위** 상자를 클릭하고 기본 선택 내용을 지웁니다.  
  
5.  **차트 데이터** 시트에서 차트 데이터가 포함된 셀 범위\(**A5**부터 **D8**까지의 셀\)를 선택합니다.  
  
6.  **데이터 소스 선택** 대화 상자에서 **확인**을 클릭합니다.  
  
##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에서 차트 컨트롤 추가  
 런타임에 동적으로 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가할 수 있습니다.  동적으로 생성된 차트는 문서를 닫을 때 문서에 호스트 컨트롤로 유지되지 않습니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
#### 프로그래밍 방식으로 워크시트에 차트 컨트롤을 추가하려면  
  
1.  `Sheet1`의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트 처리기에서 다음 코드를 삽입하여 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsExcel#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#1)]  
  
##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능 프로젝트에서 차트 컨트롤 추가  
 VSTO 추가 기능 프로젝트에서 열려 있는 워크시트에 프로그래밍 방식으로 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가할 수 있습니다.  자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
 동적으로 생성된 차트 컨트롤은 워크시트를 닫을 때 워크시트에서 호스트 컨트롤로 유지되지 않습니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
#### 프로그래밍 방식으로 워크시트에 차트 컨트롤을 추가하려면  
  
1.  다음 코드는 열려 있는 워크시트를 기반으로 하는 워크시트 호스트 항목을 생성하고 <xref:Microsoft.Office.Tools.Excel.Chart> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#9)]
     [!code-vb[Trin_Excel_Dynamic_Controls#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#9)]  
  
## 코드 컴파일  
 이 예제에는 다음과 같은 요구 사항이 있습니다.  
  
-   워크시트의 A5부터 D8까지의 범위에 저장된 차트로 작성할 데이터  
  
## 참고 항목  
 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [Chart 컨트롤](../vsto/chart-control.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  