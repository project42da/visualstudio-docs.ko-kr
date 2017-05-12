---
title: "방법: 프로그래밍 방식으로 Word의 기본 제공 대화 상자 사용"
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
  - "Word[Visual Studio에서 Office 개발], 대화 상자"
  - "대화 상자"
ms.assetid: 0c7e4338-dead-4444-868b-3b0212368455
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 방법: 프로그래밍 방식으로 Word의 기본 제공 대화 상자 사용
  Microsoft Office Word를 사용하여 작업하는 경우 사용자 입력을 위한 대화 상자를 표시해야 할 때가 있습니다.  대화 상자를 직접 만들 수도 있지만 <xref:Microsoft.Office.Interop.Word.Application> 개체의 <xref:Microsoft.Office.Interop.Word.Dialogs> 컬렉션에서 제공하는 Word의 기본 제공 대화 상자를 사용하는 것이 편리할 수도 있습니다.  이렇게 하면 열거형으로 표시되는 200가지 이상의 기본 제공 대화 상자에 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 대화 상자 표시  
 대화 상자를 표시하려면 <xref:Microsoft.Office.Interop.Word.WdWordDialog> 열거형 값 중 하나를 사용하여 표시할 대화 상자를 나타내는 <xref:Microsoft.Office.Interop.Word.Dialog> 개체를 만듭니다.  그런 다음 <xref:Microsoft.Office.Interop.Word.Dialog> 개체의 <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> 메서드를 호출합니다.  
  
 다음 코드 예제에서는 **파일 열기** 대화 상자를 표시하는 방법을 보여 줍니다.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#100](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#100)]
 [!code-vb[Trin_VstcoreWordAutomation#100](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#100)]  
  
### 런타임에 바인딩을 통해 사용할 수 있는 대화 상자 멤버 액세스  
 Word 대화 상자의 일부 속성과 메서드는 런타임에 바인딩을 통해서만 사용할 수 있습니다.  Visual Basic 프로젝트 위치 **Option Strict** 켜져 있어야 리플렉션을 사용 하 여 이러한 멤버에 액세스할 수 있습니다.  자세한 내용은 [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)을 참조하십시오.  
  
 다음 코드 예제에서는 사용 방법을 보여 줍니다.는 **Name** 속성의  **파일 열기** 대화 상자에서 Visual Basic 프로젝트나 **Option Strict** 해제 또는 C\# 프로젝트의 대상으로는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)].  이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#122](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#122)]
 [!code-vb[Trin_VstcoreWordAutomation#122](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#122)]  
  
 다음 코드 예제에서는 리플렉션을 사용 하 여 액세스 하는 방법을 보여 줍니다.는 **Name** 속성은  **파일 열기** 대화 상자에서 Visual Basic 프로젝트나 **Option Strict** 에.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#102)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 숨김 모드에서 Word 대화 상자 사용](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [리플렉션&#40;C&#35; 및 Visual Basic&#41;](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26)  
  
  