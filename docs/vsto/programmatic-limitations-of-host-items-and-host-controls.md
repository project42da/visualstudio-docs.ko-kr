---
title: "호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항"
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
  - "Office 문서[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "응용 프로그램 개발[Visual Studio에서 Office 개발], 호스트 항목"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 호스트 항목"
  - "호스트 항목[Visual Studio에서 Office 개발], 프로그래밍에 대한 제한 사항"
  - "Excel[Visual Studio에서 Office 개발], 호스트 항목"
  - "호스트 컨트롤[Visual Studio에서 Office 개발], 만들기"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "문서[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "컨트롤[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "호스트 컨트롤[Visual Studio에서 Office 개발], 메서드 및 속성에 전달"
  - "응용 프로그램 개발[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "Excel[Visual Studio에서 Office 개발], 호스트 컨트롤"
  - "호스트 컨트롤[Visual Studio에서 Office 개발], 프로그래밍에 대한 제한 사항"
  - "문서[Visual Studio에서 Office 개발], 호스트 항목"
  - "Office 문서[Visual Studio에서 Office 개발], 호스트 항목"
  - "Word[Visual Studio에서 Office 개발], 호스트 항목"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 호스트 항목"
  - "Word[Visual Studio에서 Office 개발],호스트 컨트롤"
ms.assetid: 88487946-6f3d-4ea6-8de0-dd219b8002df
caps.latest.revision: 67
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 63
---
# 호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항
  각 호스트 항목 및 호스트 컨트롤은 추가 기능을 통해 해당 네이티브 Microsoft Office Word 또는 Microsoft Office Excel 개체처럼 동작하도록 설계되었습니다. 그러나 런타임에 호스트 항목과 호스트 컨트롤의 동작과 네이티브 Office 개체 간에는 몇 가지 근본적인 차이가 있습니다.  
  
 호스트 항목 및 호스트 컨트롤에 대한 일반적인 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## 프로그래밍 방식으로 호스트 항목 만들기  
 Word 또는 Excel 개체 모델을 사용하여 런타임에 프로그래밍 방식으로 문서, 통합 문서 또는 워크시트를 만들거나 여는 경우 해당 항목은 호스트 항목이 아닙니다. 대신, 새 개체는 네이티브 Office 개체입니다. 예를 들어 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드를 사용하여 런타임에 새 Word 문서를 만드는 경우 이 문서는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목이 아닌 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 개체입니다. 마찬가지로 런타임에 <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> 메서드를 사용하여 새 워크시트를 만드는 경우, <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목이 아닌 네이티브 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체를 얻습니다.  
  
 문서 수준 프로젝트에서는 런타임에 호스트 항목을 만들 수 없습니다. 문서 수준 프로젝트에서는 디자인 타임에만 호스트 항목을 만들 수 있습니다. 자세한 내용은 [문서 호스트 항목](../vsto/document-host-item.md), [통합 문서 호스트 항목](../vsto/workbook-host-item.md) 및 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)을 참조하십시오.  
  
 VSTO 추가 기능 프로젝트에서 런타임에 <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 만들 수 있습니다. 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
## 프로그래밍 방식으로 호스트 컨트롤 만들기  
 런타임에 프로그래밍 방식으로 호스트 컨트롤을 <xref:Microsoft.Office.Tools.Word.Document> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목에 추가할 수 있습니다. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
 호스트 컨트롤은 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 또는 <xref:Microsoft.Office.Interop.Excel.Worksheet>에 추가할 수 없습니다.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, <xref:Microsoft.Office.Tools.Word.XMLNodes> 호스트 컨트롤은 프로그래밍 방식으로 워크시트 또는 문서에 추가할 수 없습니다.  
  
## 호스트 항목, 호스트 컨트롤과 네이티브 Office 개체 간 형식의 차이점 이해  
 각 호스트 항목 및 호스트 컨트롤의 경우 기본 네이티브 Microsoft Office Word 또는 Microsoft Office Excel 개체가 있습니다. 호스트 항목이나 호스트 컨트롤의 InnerObject 속성을 사용하여 기본 개체에 액세스할 수 있습니다. 그러나 해당 호스트 항목이나 호스트 컨트롤에 네이티브 Office 개체를 캐스트하는 방법은 없습니다. 네이티브 Office 개체를 호스트 항목이나 호스트 컨트롤의 형식으로 캐스트하려는 경우 <xref:System.InvalidCastException>이 throw됩니다.  
  
 호스트 항목 및 호스트 컨트롤과 기본 네이티브 Office 개체 형식 간의 차이점이 코드에 영향을 줄 수 있는 몇 가지 시나리오가 있습니다.  
  
### 호스트 컨트롤을 메서드 및 속성에 전달  
 Word에서는 매개 변수로 네이티브 Word 개체가 필요한 메서드 또는 속성에 호스트 컨트롤을 전달할 수 없습니다. 호스트 컨트롤의 InnerObject 속성을 사용하여 기본 네이티브 Word 개체를 반환해야 합니다. 예를 들어 <xref:Microsoft.Office.Tools.Word.Bookmark> 호스트 컨트롤의 <xref:Microsoft.Office.Tools.Word.Bookmark.InnerObject%2A> 속성을 메서드에 전달하여 <xref:Microsoft.Office.Interop.Word.Bookmark> 개체를 메서드에 전달할 수 있습니다.  
  
 Excel에서는 메서드 또는 속성이 기본 Excel 개체를 기대할 때 호스트 컨트롤의 InnerObject 속성을 사용하여 메서드 또는 속성에 호스트 컨트롤을 전달해야 합니다.  
  
 다음 예제에서는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 만들어 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드에 전달합니다. 코드에서는 명명된 범위의 <xref:Microsoft.Office.Tools.Excel.NamedRange.InnerObject%2A> 속성을 사용하여 <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> 메서드에서 필요한 기본 Office <xref:Microsoft.Office.Interop.Excel.Range>를 반환합니다.  
  
 [!code-csharp[Trin_VstcoreHostControlsExcel#28](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#28)]
 [!code-vb[Trin_VstcoreHostControlsExcel#28](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#28)]  
  
### 네이티브 Office 메서드 및 속성의 형식 반환  
 호스트 항목의 메서드와 속성 대부분은 호스트 항목의 기반이 되는 기본 네이티브 Office 개체를 반환합니다. 예를 들어 Excel에서 <xref:Microsoft.Office.Tools.Excel.NamedRange> 호스트 컨트롤의 <xref:Microsoft.Office.Tools.Excel.NamedRange.Parent%2A> 속성은 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목이 아닌 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체를 반환합니다. 마찬가지로 Word에서 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 호스트 컨트롤의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.Parent%2A> 속성은 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목이 아닌 <xref:Microsoft.Office.Interop.Word.Document> 개체를 반환합니다.  
  
### 호스트 컨트롤의 컬렉션 액세스  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]은 호스트 컨트롤의 각 형식에 개별 컬렉션을 제공하지 않습니다. 대신 호스트 항목의 Controls 속성을 사용하여 문서 또는 워크시트에서 모든 관리되는 컨트롤\(호스트 컨트롤 및 Windows Forms 컨트롤 모두\)을 반복한 다음 관심 있는 호스트 컨트롤의 형식과 일치하는 항목을 찾습니다. 다음 코드 예제에서는 Word 문서의 각 컨트롤을 검사하고 컨트롤이 <xref:Microsoft.Office.Tools.Word.Bookmark>인지 여부를 확인합니다.  
  
 [!code-csharp[Trin_VstcoreHostControlsWord#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/CS/ThisDocument.cs#10)]
 [!code-vb[Trin_VstcoreHostControlsWord#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/VB/ThisDocument.vb#10)]  
  
 호스트 항목의 Controls 속성에 대한 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
 Word 및 Excel 개체 모델은 문서 및 워크시트에서 네이티브 컨트롤의 컬렉션을 노출하는 속성을 포함합니다. 이러한 속성을 사용하면 관리되는 컨트롤에 액세스할 수 없습니다. 예를 들어 <xref:Microsoft.Office.Interop.Word.Document>의 <xref:Microsoft.Office.Interop.Word._Document.Bookmarks%2A> 속성 또는 <xref:Microsoft.Office.Tools.Word.Document>의 <xref:Microsoft.Office.Tools.Word.Document.Bookmarks%2A> 속성을 사용하여 문서의 각 <xref:Microsoft.Office.Tools.Word.Bookmark> 호스트 컨트롤을 열거할 수 없습니다. 이러한 속성은 문서의 <xref:Microsoft.Office.Interop.Word.Bookmark> 컨트롤만 포함하며 문서의 <xref:Microsoft.Office.Tools.Word.Bookmark> 호스트 컨트롤은 포함하지 않습니다.  
  
## 참고 항목  
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)  
  
  