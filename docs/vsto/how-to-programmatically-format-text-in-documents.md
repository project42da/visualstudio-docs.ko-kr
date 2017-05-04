---
title: "방법: 프로그래밍 방식으로 문서의 텍스트 서식 지정 | Microsoft Docs"
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
  - "서식 지정[Visual Studio에서 Office 개발]"
  - "문서[Visual Studio에서 Office 개발], 텍스트 서식 지정"
  - "텍스트[Visual Studio에서 Office 개발], 문서에서 서식 지정"
ms.assetid: 0a84893b-5ccc-4515-a2dc-95773ee8eaba
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# 방법: 프로그래밍 방식으로 문서의 텍스트 서식 지정
  <xref:Microsoft.Office.Interop.Word.Range> 개체를 사용하여 Microsoft Office Word 문서의 텍스트에 서식을 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 예제에서는 문서의 첫 번째 단락을 선택하고 글꼴 크기, 글꼴 이름 및 맞춤을 변경합니다. 그런 다음 범위를 선택하고 메시지 상자를 표시하여 코드의 다음 섹션을 실행하기 전에 일시 중지합니다. 다음 섹션에서는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목\(문서 수준 사용자 지정의 경우\) 또는 <xref:Microsoft.Office.Interop.Word.Document> 클래스\(VSTO 추가 기능의 경우\)의 Undo 메서드를 세 번 호출합니다. 표준 들여쓰기 스타일을 적용하고 메시지 상자를 표시하여 코드를 일시 중지합니다. 그런 다음 코드에서 <xref:Microsoft.Office.Tools.Word.Document.Undo%2A> 메서드를 한 번 호출하고 메시지 상자를 표시합니다.  
  
## 문서 수준 사용자 지정 예제  
  
#### 문서 수준 사용자 지정을 사용하여 텍스트의 서식을 지정하려면  
  
1.  다음 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#62](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#62)]
     [!code-vb[Trin_VstcoreWordAutomation#62](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#62)]  
  
## VSTO 추가 기능 예제  
  
#### VSTO 추가 기능을 사용하여 텍스트의 서식을 지정하려면  
  
1.  다음 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#62](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#62)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#62](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#62)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)  
  
  