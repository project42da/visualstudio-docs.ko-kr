---
title: "방법: 프로그래밍 방식으로 Visio 문서 열기 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], Visio 문서 열기"
  - "Visio[Visual Studio에서 Office 개발], Visio 문서 열기"
ms.assetid: bddb820c-bde7-4d21-a0b3-6d1968baccab
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: 프로그래밍 방식으로 Visio 문서 열기
  기존 Microsoft Office Visio 문서를 여는 메서드는 Open 및 OpenEx의 두 가지가 있습니다.OpenEx 메서드는 호출자가 문서를 여는 방법을 지정할 수 있는 인수를 제공한다는 점을 제외하면 Open 메서드와 동일합니다.  
  
 개체 모델에 대한 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Documents.Open](HV10070351) 메서드 및  [Microsoft.Office.Interop.Visio.Documents.OpenEx](HV10071456) 메서드를 참조하세요.  
  
## Visio 문서 열기  
  
#### Visio 문서를 열려면  
  
-   Microsoft.Office.Interop.Visio.Documents.Open 메서드를 호출하고 Visio 문서의 정규화된 경로를 제공합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#5)]  
  
## 지정된 인수로 Visio 문서 열기  
  
#### Visio 문서를 읽기 전용 및 도킹하여 열려면  
  
-   Microsoft.Office.Interop.Visio.Documents.OpenEx 메서드를 호출하여 Visio 문서의 정규화된 경로를 제공하고 사용하려는 인수\(이 경우, 도킹됨 및 읽기 전용\)를 포함합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#6)]  
  
## 코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   이름이 `myDrawing.vsd`인 Visio 문서가 내 문서 폴더\(Windows XP 및 이전\) 또는 문서 폴더\(Windows Vista\)의 `Test` 디렉터리에 있어야 합니다.  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  