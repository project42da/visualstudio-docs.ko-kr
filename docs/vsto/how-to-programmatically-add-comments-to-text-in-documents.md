---
title: "방법: 프로그래밍 방식으로 문서의 텍스트에 메모 추가"
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
  - "메모, 문서에 추가"
  - "문서[Visual Studio에서 Office 개발], 메모 추가"
ms.assetid: 4e396e31-01bf-424c-be6b-9a1806bcd572
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: 프로그래밍 방식으로 문서의 텍스트에 메모 추가
  Document 클래스의 Comments 속성은 Microsoft Office Word 문서의 텍스트 범위에 메모를 추가합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 예제에서는 문서의 첫 번째 단락에 메모를 추가합니다.  
  
### 문서 수준 사용자 지정에서 텍스트에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.Document.Comments%2A> 속성의 <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> 메서드를 호출하고 범위 및 메모 텍스트를 제공합니다. 다음 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#118](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#118)]
     [!code-vb[Trin_VstcoreWordAutomation#118](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#118)]  
  
### VSTO 추가 기능에서 텍스트에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word._Document.Comments%2A> 속성의 <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> 메서드를 호출하고 범위 및 메모 텍스트를 제공합니다.  
  
     다음 코드 예제에서는 활성 문서에 메모를 추가합니다. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#118](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#118)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#118](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#118)]  
  
## 강력한 프로그래밍  
 Word에서 메모에 추가하는 사용자 이니셜을 변경하려면 <xref:Microsoft.Office.Interop.Word._Application.UserInitials%2A> 속성을 사용합니다.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서에서 모든 메모 제거](../vsto/how-to-programmatically-remove-all-comments-from-documents.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)  
  
  