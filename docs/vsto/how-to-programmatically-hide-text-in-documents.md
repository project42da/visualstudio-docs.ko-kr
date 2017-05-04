---
title: "방법: 프로그래밍 방식으로 문서에서 텍스트 숨기기 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 텍스트 숨기기"
  - "텍스트[Visual Studio에서 Office 개발], 문서에서 숨기기"
ms.assetid: f5ced4ec-22ca-463b-b963-d34ce631b486
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: 프로그래밍 방식으로 문서에서 텍스트 숨기기
  텍스트의 특정 범위에 대해 <xref:Microsoft.Office.Interop.Word.Range.Font%2A>의 <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> 속성을 설정하여 문서에서 텍스트를 숨길 수 있습니다.  
  
 예를 들어 문서를 프린터로 보내기 전에 <xref:Microsoft.Office.Tools.Word.Bookmark>\(문서 수준 사용자 지정\) 또는 <xref:Microsoft.Office.Interop.Word.Bookmark>\(VSTO 추가 기능\) 내에 일시적으로 텍스트를 숨길 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 문서를 인쇄하는 동안 책갈피 컨트롤에서 텍스트를 숨기려면  
  
1.  지정된 범위에 있는 모든 텍스트를 숨기는 프로시저를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#105](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#105)]
     [!code-vb[Trin_VstcoreWordAutomation#105](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#105)]  
  
2.  지정된 범위에 있는 모든 텍스트를 표시하는 프로시저를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#106](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#106)]
     [!code-vb[Trin_VstcoreWordAutomation#106](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#106)]  
  
3.  책갈피의 범위를 `HideText` 메서드로 전달하고, 문서를 인쇄한 다음 동일한 범위를 `UnhideText` 메서드로 전달합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다. 이 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#107](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#107)]
     [!code-vb[Trin_VstcoreWordAutomation#107](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#107)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다. 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#107)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#107)]  
  
## 코드 컴파일  
 이 코드 예제에서는 문서에 `bookmark1`이라는 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤\(문서 수준 사용자 지정\) 또는 <xref:Microsoft.Office.Interop.Word.Bookmark> 컨트롤\(VSTO 추가 기능\)이 포함된다고 가정합니다.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서 인쇄](../vsto/how-to-programmatically-print-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 책갈피 텍스트 업데이트](../vsto/how-to-programmatically-update-bookmark-text.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  