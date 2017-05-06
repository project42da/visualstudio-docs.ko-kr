---
title: "방법: 프로그래밍 방식으로 Visio 문서 인쇄"
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
  - "Visio[Visual Studio에서 Office 개발], Visio 문서 인쇄"
  - "문서[Visual Studio에서 Office 개발], Visio 문서 인쇄"
ms.assetid: 606a2678-5eb8-40b2-a50a-305cecb1b3d4
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 프로그래밍 방식으로 Visio 문서 인쇄
  전체 Microsoft Office Visio 문서 또는 특정 페이지만 인쇄할 수 있습니다.  
  
 인쇄 방법에 대한 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Document.Print](HV10070345) 메서드 및 [Microsoft.Office.Interop.Visio.Page.Print](HV10070404) 메서드를 참조하세요.  
  
## Visio 문서 인쇄  
  
#### 전체 문서를 인쇄하려면  
  
-   인쇄하려는 Microsoft.Office.Interop.Visio.Document 개체의 Microsoft.Office.Interop.Visio.Document.Print 메서드를 호출합니다.  
  
     다음 코드 예제에서는 활성 문서를 인쇄합니다. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#8)]  
  
## Visio 문서 페이지 인쇄  
  
#### 문서 페이지를 인쇄하려면  
  
-   인쇄하려는 Microsoft.Office.Interop.Visio.Pages 개체의 Microsoft.Office.Interop.Visio.Pages.Print 메서드를 호출합니다.  
  
     다음 코드 예제에서는 활성 문서의 첫 번째 페이지를 인쇄합니다. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#9)]  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 열기](../vsto/how-to-programmatically-open-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  