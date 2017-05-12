---
title: "방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색"
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
  - "범위, 시작 및 끝 문자 검색"
  - "끝 문자"
  - "시작 문자"
  - "문서[Visual Studio에서 Office 개발], 범위 검색"
ms.assetid: 734c630c-abc9-491d-94b6-429d1fc7a4cc
caps.latest.revision: 37
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 36
---
# 방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색
  이 예제는 범위의 시작 및 끝 위치의 문자 위치를 가져오는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 문서 수준 사용자 지정에서 범위의 시작 및 끝 글자를 가져오려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 및 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 속성 값을 가져옵니다. 다음 코드 예제에서는 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#25](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#25)]
     [!code-vb[Trin_VstcoreWordAutomation#25](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#25)]  
  
### VSTO 추가 기능을 사용하여 범위의 시작 및 끝 문자를 가져오려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 및 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 속성 값을 가져옵니다. 다음 코드 예제에서는 활성 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#25)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 또는 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시 제외](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [방법: 프로그래밍 방식으로 문서의 문자 수 세기](../vsto/how-to-programmatically-count-characters-in-documents.md)  
  
  