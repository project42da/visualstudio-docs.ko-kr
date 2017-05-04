---
title: "방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 검색"
  - "텍스트[Visual Studio에서 Office 개발], 문서에서 검색"
  - "텍스트[Visual Studio에서 Office 개발], 텍스트 검색"
  - "텍스트 검색, 문서"
  - "텍스트 검색, 텍스트 바꾸기"
ms.assetid: a66962f5-eeb9-4dc6-a70f-9039ab437a63
caps.latest.revision: 51
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 50
---
# 방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기
  <xref:Microsoft.Office.Interop.Word.Find> 개체는 <xref:Microsoft.Office.Interop.Word.Selection> 및 <xref:Microsoft.Office.Interop.Word.Range> 개체 둘 다의 멤버이며, 둘 중 하나를 사용하여 Microsoft Office Word 문서에서 텍스트를 검색할 수 있습니다.  바꾸기 명령은 찾기 명령의 확장입니다.  
  
 <xref:Microsoft.Office.Interop.Word.Find> 개체를 사용하여 Microsoft Office Word 문서를 반복하고 특정 텍스트, 서식 또는 스타일을 검색한 다음 <xref:Microsoft.Office.Interop.Word.Find.Replacement%2A> 속성을 사용하여 찾은 항목을 바꿉니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## Selection 개체 사용  
 <xref:Microsoft.Office.Interop.Word.Selection> 개체를 사용하여 텍스트를 찾는 경우 지정한 검색 조건은 현재 선택한 텍스트에 대해서만 적용됩니다.  <xref:Microsoft.Office.Interop.Word.Selection>이 삽입 지점이면 문서가 검색됩니다.  검색 조건과 일치하는 항목이 발견되면 자동으로 선택됩니다.  
  
 <xref:Microsoft.Office.Interop.Word.Find> 조건은 누적되며, 이는 조건이 이전 검색 조건에 추가됨을 의미합니다.  검색 전에 <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> 메서드를 사용하여 이전 검색의 서식을 지웁니다.  
  
#### Selection 개체를 사용하여 텍스트를 찾으려면  
  
1.  변수에 검색 문자열을 할당합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#68](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#68)]
     [!code-vb[Trin_VstcoreWordAutomation#68](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#68)]  
  
2.  이전 검색의 서식을 지웁니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#69](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#69)]
     [!code-vb[Trin_VstcoreWordAutomation#69](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#69)]  
  
3.  검색을 실행하고 결과가 포함된 메시지 상자를 표시합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#70](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#70)]
     [!code-vb[Trin_VstcoreWordAutomation#70](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#70)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#67](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#67)]
 [!code-vb[Trin_VstcoreWordAutomation#67](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#67)]  
  
## Range 개체 사용  
 <xref:Microsoft.Office.Interop.Word.Range> 개체를 사용하면 사용자 인터페이스에 아무것도 표시하지 않고 텍스트를 검색할 수 있습니다.  검색 조건과 일치하는 텍스트가 있는 경우 <xref:Microsoft.Office.Interop.Word.Find> 개체가 **True**를 반환하고, 그렇지 않은 경우 **False**를 반환합니다.  또한 텍스트가 발견되는 경우 검색 조건과 일치하도록 <xref:Microsoft.Office.Interop.Word.Range> 개체를 다시 정의합니다.  
  
#### Range 개체를 사용하여 텍스트를 찾으려면  
  
1.  문서의 두 번째 단락으로 구성된 <xref:Microsoft.Office.Interop.Word.Range> 개체를 정의합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#72](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#72)]
     [!code-vb[Trin_VstcoreWordAutomation#72](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#72)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다.  이 예제에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#72](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#72)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#72](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#72)]  
  
2.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Find%2A> 속성을 사용하여 먼저 기존 서식 옵션을 모두 지운 다음 문자열 **find me**를 검색합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#73](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#73)]
     [!code-vb[Trin_VstcoreWordAutomation#73](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#73)]  
  
3.  메시지 상자에 검색 결과를 표시하고 <xref:Microsoft.Office.Interop.Word.Range>를 선택하여 표시되도록 합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#74](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#74)]
     [!code-vb[Trin_VstcoreWordAutomation#74](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#74)]  
  
     검색에 실패하면 두 번째 단락이 선택됩니다. 성공하면 검색 조건이 표시됩니다.  
  
 다음 예제에서는 문서 수준 사용자 지정의 전체 코드를 보여 줍니다.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 코드를 실행합니다.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#71](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#71)]
 [!code-vb[Trin_VstcoreWordAutomation#71](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#71)]  
  
 다음 예제에서는 VSTO 추가 기능의 전체 코드를 보여 줍니다.  이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
 [!code-csharp[Trin_VstcoreWordAutomationAddIn#71](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#71)]
 [!code-vb[Trin_VstcoreWordAutomationAddIn#71](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#71)]  
  
## 문서에서 텍스트 검색 및 바꾸기  
 다음 코드는 현재 선택 영역을 검색하고 **find me** 문자열의 모든 발생을 **Found** 문자열로 바꿉니다.  
  
#### 문서에서 텍스트를 검색하고 바꾸려면  
  
1.  프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에 다음 예제 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#75](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#75)]
     [!code-vb[Trin_VstcoreWordAutomation#75](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#75)]  
  
     <xref:Microsoft.Office.Interop.Word.Find> 클래스에는 <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> 메서드가 있고 <xref:Microsoft.Office.Interop.Word.Replacement> 클래스에도 자체 <xref:Microsoft.Office.Interop.Word.Replacement.ClearFormatting%2A> 메서드가 있습니다.  찾기 및 바꾸기 작업을 수행하는 경우 두 개체의 ClearFormatting 메서드를 사용해야 합니다.  <xref:Microsoft.Office.Interop.Word.Find> 개체에서만 사용하는 경우 대체 텍스트에서 예기치 않은 결과가 발생할 수 있습니다.  
  
2.  <xref:Microsoft.Office.Interop.Word.Find> 개체의 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드를 사용하여 찾은 각 항목을 바꿉니다.  바꿀 항목을 지정하려면 *Replace* 매개 변수를 사용합니다.  이 매개 변수는 다음 <xref:Microsoft.Office.Interop.Word.WdReplace> 값 중 하나일 수 있습니다.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceAll>은 찾은 항목을 모두 바꿉니다.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceNone>은 찾은 항목을 바꾸지 않습니다.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceOne>은 찾은 첫 번째 항목을 바꿉니다.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  