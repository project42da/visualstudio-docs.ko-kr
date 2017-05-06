---
title: "방법: 프로그래밍 방식으로 Visio 문서 닫기"
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
  - "문서[Visual Studio에서 Office 개발], Visio 문서 닫기"
  - "Visio[Visual Studio에서 Office 개발], Visio 문서 닫기"
ms.assetid: 59c0e215-a4c1-4b39-a491-37534f172705
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 프로그래밍 방식으로 Visio 문서 닫기
  Microsoft.Office.Interop.Visio.Document.Close 메서드를 사용하여 활성 Microsoft Office Visio 문서를 닫을 수 있습니다.  
  
 이 메서드에 대한 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Document.Close](HV10070225) 메서드를 참조하세요.  
  
## 활성 문서 닫기  
  
#### 활성 문서를 닫으려면  
  
-   Microsoft.Office.Interop.Visio.Document.Close 메서드를 호출하여 활성 문서를 닫습니다.  
  
     다음 코드 예제를 사용하려면 Visio용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#7)]  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 열기](../vsto/how-to-programmatically-open-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  