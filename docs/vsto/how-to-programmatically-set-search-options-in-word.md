---
title: "방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정"
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
  - "문서[Visual Studio에서 Office 개발], 검색 옵션"
  - "검색, Word 옵션"
  - "설정, Word 검색 옵션"
  - "Word, 검색 옵션"
ms.assetid: 4412b4e8-2868-4afb-a593-983603ef9b02
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 45
---
# 방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정
  Microsoft Office Word 문서에서 선택 영역에 대한 검색 옵션을 설정하는 데는 두 가지 방법이 있습니다.  
  
-   <xref:Microsoft.Office.Interop.Word.Find> 개체의 개별 속성을 설정합니다.  
  
-   <xref:Microsoft.Office.Interop.Word.Find> 개체의 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드 인수를 사용합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## Find 개체의 속성 사용  
 다음 코드에서는 현재 선택 영역 내의 텍스트를 검색하기 위한 <xref:Microsoft.Office.Interop.Word.Find> 개체의 속성을 설정합니다.  검색 방향, 줄 바꿈, 검색할 텍스트 등과 같은 검색 조건은 <xref:Microsoft.Office.Interop.Word.Find> 개체의 속성입니다.  
  
 C\# 코드를 작성하는 경우에는 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드에서 동일한 속성을 매개 변수로 지정해야 하므로 <xref:Microsoft.Office.Interop.Word.Find> 개체의 각 속성을 설정하는 것이 오히려 불편할 수 있습니다.  따라서 이 예제에서는 Visual Basic 코드만 보여 줍니다.  
  
#### Find 개체를 사용하여 검색 옵션을 설정하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Find> 개체의 속성을 설정하여 선택 영역을 앞쪽으로 이동하며 **find me**라는 텍스트를 검색합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#76)]  
  
## Execute 메서드 인수 사용  
 다음 코드에서는 <xref:Microsoft.Office.Interop.Word.Find> 개체의 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드를 사용하여 현재 선택 영역 내의 텍스트를 검색합니다.  검색 방향, 줄 바꿈, 검색할 텍스트 등과 같은 검색 조건은 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드의 매개 변수로 전달됩니다.  
  
#### Execute 메서드 인수를 사용하여 검색 옵션을 설정하려면  
  
1.  검색 조건을 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드의 매개 변수로 전달하여 선택 영역을 앞쪽으로 이동하며 **find me**라는 텍스트를 검색합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#77](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#77)]
     [!code-vb[Trin_VstcoreWordAutomation#77](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#77)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  