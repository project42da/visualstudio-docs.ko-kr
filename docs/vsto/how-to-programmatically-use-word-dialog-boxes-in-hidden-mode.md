---
title: "방법: 프로그래밍 방식으로 숨김 모드에서 Word 대화 상자 사용 | Microsoft Docs"
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
  - "대화 상자, Word에서 숨김 모드"
  - "숨겨진 대화 상자"
  - "Word[Visual Studio에서 Office 개발], 대화 상자"
ms.assetid: a5619325-8b54-41f1-becb-3f6eae7e4a6b
caps.latest.revision: 48
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 47
---
# 방법: 프로그래밍 방식으로 숨김 모드에서 Word 대화 상자 사용
  Microsoft Office Word에서 기본 제공 대화 상자를 사용자에게 표시하지 않고 호출하여 메서드 호출 한 번으로 복잡한 작업을 수행할 수 있습니다.  <xref:Microsoft.Office.Interop.Word.Dialog> 개체의 <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> 메서드를 호출하지 않고 <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> 메서드를 사용하여 이 작업을 수행할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 예제  
 다음 코드 예제에서는 숨김 모드에서 **페이지 설정** 대화 상자를 사용하여 사용자 입력 없이 여러 페이지 설정 속성을 설정하는 방법을 보여 줍니다.  이 예제에서는 <xref:Microsoft.Office.Interop.Word.Dialog> 개체를 사용하여 사용자 지정 페이지 크기를 구성합니다.  위쪽 여백, 아래쪽 여백 등의 페이지 설정에 대한 특정 설정은 <xref:Microsoft.Office.Interop.Word.Dialog> 개체의 런타임에 바인딩되는 속성으로 사용할 수 있습니다.  이러한 속성은 Word에서 런타임에 동적으로 만들어집니다.  
  
 다음 예제에서는 **Option Strict**가 해제된 Visual Basic 프로젝트와 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]를 대상으로 하는 Visual C\# 프로젝트에서 이 작업을 수행하는 방법을 보여 줍니다.  이러한 프로젝트에서는 Visual Basic 및 Visual C\# 컴파일러에서 런타임에 바인딩 기능을 사용할 수 있습니다.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#123](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#123)]
 [!code-vb[Trin_VstcoreWordAutomation#123](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#123)]  
  
 다음 예제에서는 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다. 여기서 **Option Strict** 있습니다.  이러한 프로젝트에서는 리플렉션을 사용하여 런타임에 바인딩되는 속성에 액세스해야 합니다.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#104)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 Word의 기본 제공 대화 상자 사용](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)   
 [리플렉션&#40;C&#35; 및 Visual Basic&#41;](../Topic/Reflection%20(C%23%20and%20Visual%20Basic).md)  
  
  