---
title: "방법: 프로그래밍 방식으로 문서에서 모든 메모 제거 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 메모 제거"
  - "메모, 문서에서 제거"
ms.assetid: 920de39a-3b6d-4682-bca6-f4b4dedda1ac
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 프로그래밍 방식으로 문서에서 모든 메모 제거
  DeleteAllComments 메서드를 사용하여 Microsoft Office Word 문서에서 모든 메모를 제거합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 문서 수준 사용자 지정의 일부인 문서에서 모든 메모를 제거하려면  
  
1.  프로젝트에서 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> 메서드를 호출합니다. 이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#119](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#119)]
     [!code-vb[Trin_VstcoreWordAutomation#119](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#119)]  
  
### VSTO 추가 기능을 사용하여 문서에서 모든 메모를 제거하려면  
  
1.  메모를 제거하려는 <xref:Microsoft.Office.Interop.Word.Document>의 <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> 메서드를 호출합니다.  
  
     다음 코드 예제에서는 활성 문서에서 모든 메모를 제거합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#119)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#119)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 텍스트에 메모 추가](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)  
  
  