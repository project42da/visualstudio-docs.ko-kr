---
title: "방법: ListObject 컨트롤 크기 조정"
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
  - "컨트롤[Visual Studio에서 Office 개발], 크기 조정"
  - "ListObject 컨트롤, 크기 조정"
ms.assetid: a4c7dceb-7b55-447e-9b88-c3596a2fc361
caps.latest.revision: 50
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: ListObject 컨트롤 크기 조정
  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기는 Microsoft Office Excel 통합 문서에 추가할 때 설정하지만 나중에 크기를 조정할 수 있습니다. 예를 들어 2열로 된 목록을 3열로 변경할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 문서 수준 프로젝트에서는 디자인 타임 또는 런타임에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기를 조정할 수 있습니다. VSTO 추가 기능 프로젝트에서는 런타임에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기를 조정할 수 있습니다.  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 ListObject 컨트롤 크기 조정](#designtime)  
  
-   [런타임에 문서 수준 프로젝트에서 ListObject 컨트롤 크기 조정](#runtimedoclevel)  
  
-   [런타임에 VSTO 추가 기능 프로젝트에서 ListObject 컨트롤 크기 조정](#runtimeaddin)  
  
 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에 대한 자세한 내용은 [ListObject 컨트롤](../vsto/listobject-control.md)을 참조하세요.  
  
 ![비디오에 링크](~/docs/data-tools/media/playvideo.gif "비디오에 링크") 관련 동영상 데모는 [어떻게 할까요?: 런타임에 데이터 바인딩된 목록 개체에 열 추가](http://go.microsoft.com/fwlink/?LinkID=130318)를 참조하세요.  
  
##  <a name="designtime"></a> 디자인 타임에 ListObject 컨트롤 크기 조정  
 목록 크기를 조정하려면 크기 조정 핸들 중 하나를 클릭하여 끌거나 **목록 크기 조정** 대화 상자에서 크기를 재정의합니다.  
  
#### 목록 크기 조정 대화 상자를 사용하여 목록 크기를 조정하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  **목록**을 가리키고 바로 가기 메뉴에서 **목록 크기 조정**을 클릭합니다.  
  
3.  목록 크기를 정의하는 데 사용할 셀을 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에서 ListObject 컨트롤 크기 조정  
 <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> 메서드를 사용하여 런타임에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기를 조정할 수 있습니다. 이 메서드를 사용하여 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 워크시트의 새 위치로 이동할 수는 없습니다. 머리글은 동일한 행에 유지되고 크기 조정된 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤은 원래 목록 개체에 겹쳐져야 합니다. 크기 조정된 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에는 하나의 머리글 행과 하나 이상의 데이터 행이 있어야 합니다.  
  
#### 프로그래밍 방식으로 목록 개체의 크기를 조정하려면  
  
1.  `Sheet1`에서 **A1**부터 **B3**까지의 셀을 포함하도록 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 만듭니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#6)]  
  
2.  **A1**부터 **C5**까지의 셀을 포함하도록 목록의 크기를 조정합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#7)]  
  
##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능 프로젝트에서 ListObject 크기 조정  
 런타임에 열려 있는 워크시트에서 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기를 조정할 수 있습니다. VSTO 추가 기능을 사용하여 워크시트에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 추가하는 방법에 대한 자세한 내용은 [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)를 참조하세요.  
  
#### 프로그래밍 방식으로 목록 개체의 크기를 조정하려면  
  
1.  `Sheet1`에서 **A1**부터 **B3**까지의 셀을 포함하도록 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 만듭니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#12)]  
  
2.  **A1**부터 **C5**까지의 셀을 포함하도록 목록의 크기를 조정합니다.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#13)]  
  
## 참고 항목  
 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)   
 [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [방법: 책갈피 컨트롤 크기 조정](../vsto/how-to-resize-bookmark-controls.md)   
 [방법: NamedRange 컨트롤 크기 조정](../vsto/how-to-resize-namedrange-controls.md)  
  
  