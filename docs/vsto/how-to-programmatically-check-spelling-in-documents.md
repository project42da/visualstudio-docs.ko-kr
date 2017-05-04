---
title: "방법: 프로그래밍 방식으로 문서에서 맞춤법 검사 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 맞춤법 검사"
  - "맞춤법 검사기, 문서"
ms.assetid: 5bbe3a8d-fc65-4f57-bd63-5bb549dbc4bd
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# 방법: 프로그래밍 방식으로 문서에서 맞춤법 검사
  문서에서 맞춤법을 검사하려면 <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> 메서드를 사용합니다.  이 메서드는 제공된 매개 변수의 맞춤법이 정확한지 여부를 나타내는 부울 값을 반환합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 맞춤법을 검사하고 결과를 메시지 상자에 표시하려면  
  
1.  <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> 메서드를 호출하고 맞춤법 오류를 검사할 텍스트의 범위를 전달합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#113](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#113)]
     [!code-vb[Trin_VstcoreWordAutomation#113](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#113)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  