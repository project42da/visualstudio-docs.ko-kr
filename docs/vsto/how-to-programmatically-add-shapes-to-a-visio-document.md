---
title: "방법: 프로그래밍 방식으로 Visio 문서에 셰이프 추가"
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
  - "Visio[Visual Studio에서 Office 개발], Visio 셰이프 추가"
  - "셰이프[Visual Studio에서 Office 개발], Visio 셰이프 추가"
ms.assetid: 29613237-88f5-41a7-9e13-cfa177f41221
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 프로그래밍 방식으로 Visio 문서에 셰이프 추가
  스텐실에서 마스터를 검색하고 활성 페이지로 셰이프를 끌어 놓아 Microsoft Office Visio 문서에 셰이프를 추가할 수 있습니다.  
  
 자세한 내용은 [Microsoft.Office.Interop.Visio.Documents.Add](HV10069241) 메서드, [Microsoft.Office.Interop.Visio.Application.ActivePage](HV10069528) 속성 및 [Microsoft.Office.Interop.Visio.Page.Drop](HV10070273) 메서드에 대한 VBA 참조 설명서를 참조하세요.  
  
## Visio 문서에 셰이프 추가  
  
#### Visio 문서를 셰이프를 추가하려면  
  
-   문서를 활성화하고 Documents.Masters 컬렉션에서 마스터를 검색하여 활성 문서에 셰이프를 끌어 놓습니다. 인덱스 또는 마스터 이름을 사용하여 마스터를 검색할 수 있습니다.  
  
     다음 코드 예제에서는 빈 Visio 문서를 만든 다음 **기본 셰이프** 스텐실이 도킹된 상태에서 엽니다. 그러면 코드에서 여러 셰이프를 검색하여 활성 페이지에 끌어 놓습니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#13)]  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [Visio 셰이프 작업](../vsto/working-with-visio-shapes.md)   
 [방법: 프로그래밍 방식으로 Visio 문서에서 셰이프 복사 및 붙여넣기](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  