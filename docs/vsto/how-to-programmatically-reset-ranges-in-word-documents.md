---
title: "방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 범위 다시 설정"
  - "범위, 문서에서 다시 설정"
ms.assetid: 45ea9434-e548-4d24-938f-4f1ffa5010d0
caps.latest.revision: 39
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 38
---
# 방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정
  <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> 메서드를 사용하여 Microsoft Office Word 문서에서 기존의 범위의 크기를 조정합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 기존 범위를 다시 설정하려면  
  
1.  문서의 처음 7자로 시작하는 초기 범위를 설정합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#43](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#43)]
     [!code-vb[Trin_VstcoreWordAutomation#43](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#43)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 코드에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#43](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#43)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#43](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#43)]  
  
2.  <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A>를 사용하여 두 번째 문장에서 범위를 시작하고 다섯 번째 문장 끝에서 종료합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#44](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#44)]
     [!code-vb[Trin_VstcoreWordAutomation#44](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#44)]  
  
## 문서 수준 사용자 지정 예제  
  
#### 문서 수준 사용자 지정에서 기존 범위를 다시 설정하려면  
  
1.  다음 예제에서는 문서 수준 사용자 지정의 전체 예를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#42](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#42)]
     [!code-vb[Trin_VstcoreWordAutomation#42](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#42)]  
  
## VSTO 추가 기능 예제  
  
#### VSTO 추가 기능에서 기존 범위를 다시 설정하려면  
  
1.  다음 예제에서는 VSTO 추가 기능의 전체 예를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#42](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#42)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#42](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#42)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 또는 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)  
  
  