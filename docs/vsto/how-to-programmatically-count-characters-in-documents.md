---
title: "방법: 프로그래밍 방식으로 문서의 문자 수 세기"
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
  - "문자, 문서에서 수 세기"
  - "문서의 문자 수 세기"
  - "문서[Visual Studio에서 Office 개발], 문자 수 세기"
ms.assetid: ab64fe87-896a-4b56-bdf8-91c4326b540e
caps.latest.revision: 37
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 36
---
# 방법: 프로그래밍 방식으로 문서의 문자 수 세기
  문서에서 첫 번째 문자는 문자 위치 0에 있는 문자이며 삽입 지점을 나타냅니다. 마지막 문자 위치는 문서에 있는 총 문자 수와 같습니다.<xref:Microsoft.Office.Interop.Word.Characters> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Characters.Count%2A> 속성을 사용하여 문서에 있는 문자 수를 확인할 수 있습니다.  
  
 공백, 단락 표시 및 일반적으로 숨겨져 있는 다른 문자를 포함하여 문서에 있는 모든 문자 수가 계산됩니다. 단락 표시도 포함되므로 새로 만든 빈 문서도 한 개의 문자 수를 반환합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 문서 수준 사용자 지정에서 문자 수를 표시하려면  
  
1.  전체 문서를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#98](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#98)]
     [!code-vb[Trin_VstcoreWordAutomation#98](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#98)]  
  
2.  메시지 상자에 문서의 문자 수를 표시합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#99](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#99)]
     [!code-vb[Trin_VstcoreWordAutomation#99](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#99)]  
  
### VSTO 추가 기능에서 문자 수를 표시하려면  
  
1.  전체 문서를 선택합니다. 다음 예제에서는 활성 문서를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#98](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#98)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#98](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#98)]  
  
2.  메시지 상자에 문서의 문자 수를 표시합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#99](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#99)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#99](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#99)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)  
  
  