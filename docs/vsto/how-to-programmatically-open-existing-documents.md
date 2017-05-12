---
title: "방법: 프로그래밍 방식으로 기존 문서 열기"
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
  - "문서[Visual Studio에서 Office 개발], 열기"
  - "Word[Visual Studio에서 Office 개발], 문서 열기"
ms.assetid: 08f7fe4b-d96d-4a0c-b32a-aa7fd7992316
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: 프로그래밍 방식으로 기존 문서 열기
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 메서드는 정규화된 경로와 파일 이름으로 지정된 기존 Microsoft Office Word 문서를 엽니다.  이 메서드는 열려 있는 문서를 나타내는 <xref:Microsoft.Office.Interop.Word.Document>를 반환합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 문서를 열려면  
  
-   <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 메서드를 호출하고 문서의 경로를 지정합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#5)]
     [!code-vb[Trin_VstcoreWordAutomation#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#5)]  
  
### 문서를 읽기 전용으로 열려면  
  
-   <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 메서드를 호출하고 문서의 경로를 지정한 다음 메서드 호출에서 *ReadOnly* 인수를 **True**로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#6)]
     [!code-vb[Trin_VstcoreWordAutomation#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#6)]  
  
## 코드 컴파일  
 이 코드 예제를 실행하려면 다음이 필요합니다.  
  
-   C 드라이브의 Test라는 디렉터리에 NewDocument.doc라는 문서가 있어야 합니다.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 새 문서 만들기](../vsto/how-to-programmatically-create-new-documents.md)   
 [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  