---
title: "방법: 프로그래밍 방식으로 문서의 범위 확장 | Microsoft Docs"
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
  - "범위, 확장"
  - "문서[Visual Studio에서 Office 개발], 범위 확장"
ms.assetid: 055af7a4-13d5-4236-b5fb-a112721482c5
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 방법: 프로그래밍 방식으로 문서의 범위 확장
  Microsoft Office Word 문서에서 <xref:Microsoft.Office.Interop.Word.Range> 개체를 정의한 후 <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> 및 <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드를 사용하여 해당 개체의 시작점과 끝점을 변경합니다.<xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> 메서드와 <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드는 *Unit*과 *Count*라는 두 개의 인수를 동일하게 사용합니다.*Count* 인수는 이동할 단위의 수이고, *Unit* 인수는 다음 <xref:Microsoft.Office.Interop.Word.WdUnits> 값 중 하나가 될 수 있습니다.  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCharacter>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdWord>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSentence>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdParagraph>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSection>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdStory>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCell>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdColumn>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdRow>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdTable>  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 예제에서 일곱 개의 문자로 구성된 범위를 정의합니다. 그런 다음 범위의 시작 위치를 원래 시작 위치에서 일곱 문자 뒤로 이동합니다. 범위의 끝 위치는 원래 시작 위치에서 일곱 문자 뒤에 있으므로 범위를 변경한 결과에는 문자가 포함되지 않습니다.  그런 다음 이 코드에서는 끝 위치를 현재 끝 위치에서 일곱 문자 뒤로 이동합니다.  
  
### 범위를 확장하려면  
  
1.  문자의 범위를 정의합니다. 자세한 내용은 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)을 참조하세요.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#39](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#39)]
     [!code-vb[Trin_VstcoreWordAutomation#39](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#39)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#39](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#39)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#39](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#39)]  
  
2.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> 메서드를 사용하여 범위의 시작 위치를 옮깁니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#40](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#40)]
     [!code-vb[Trin_VstcoreWordAutomation#40](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#40)]  
  
3.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드를 사용하여 범위의 끝 위치를 옮깁니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#41](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#41)]
     [!code-vb[Trin_VstcoreWordAutomation#41](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#41)]  
  
## 문서 수준 사용자 지정 코드  
  
#### 문서 수준 사용자 지정의 범위를 확장하려면  
  
1.  다음 예제에서는 문서 수준 사용자 지정의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#38](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#38)]
     [!code-vb[Trin_VstcoreWordAutomation#38](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#38)]  
  
## VSTO 추가 기능 코드  
  
#### 응용 프로그램 수준 VSTO 추가 기능의 범위를 확장하려면  
  
1.  다음 예제에서는 VSTO 추가 기능의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#38](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#38)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#38](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#38)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 또는 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시 제외](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  