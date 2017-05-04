---
title: "방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색 | Microsoft Docs"
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
  - "순환, 문서에서 찾은 항목"
  - "문서[Visual Studio에서 Office 개발], 검색"
  - "텍스트[Visual Studio에서 Office 개발], 문서에서 검색"
ms.assetid: 68dc41b1-eb96-4697-ac93-1a88c862ebad
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색
  <xref:Microsoft.Office.Interop.Word.Find> 클래스에는 검색 항목을 찾을 때마다 **true**를 반환하는 <xref:Microsoft.Office.Interop.Word.Find.Found%2A> 속성이 있습니다.<xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드를 사용하여 <xref:Microsoft.Office.Interop.Word.Range>에서 찾은 모든 인스턴스를 순환 검색할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 찾은 항목을 순환 검색하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range> 개체를 선언합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#79](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#79)]
     [!code-vb[Trin_VstcoreWordAutomation#79](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#79)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#79)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#79)]  
  
2.  루프에서 <xref:Microsoft.Office.Interop.Word.Find.Found%2A> 속성을 사용하여 문서의 문자열 항목을 모두 검색하고 문자열을 찾을 때마다 정수 변수를 1씩 증분합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#80](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#80)]
     [!code-vb[Trin_VstcoreWordAutomation#80](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#80)]  
  
3.  메시지 상자에는 문자열이 발견된 횟수가 표시됩니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#81](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#81)]
     [!code-vb[Trin_VstcoreWordAutomation#81](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#81)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
## 문서 수준 사용자 지정 예제  
  
#### 문서 수준 사용자 지정에서 항목을 순환 검색하려면  
  
1.  다음 예제에서는 문서 수준 사용자 지정의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#78](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#78)]
     [!code-vb[Trin_VstcoreWordAutomation#78](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#78)]  
  
## VSTO 추가 기능 예제  
  
#### VSTO 추가 기능에서 항목을 순환 검색하려면  
  
1.  다음 예제에서는 VSTO 추가 기능의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#78)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#78)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  