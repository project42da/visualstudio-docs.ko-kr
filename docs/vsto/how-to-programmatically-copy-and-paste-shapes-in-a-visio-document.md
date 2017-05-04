---
title: "방법: 프로그래밍 방식으로 Visio 문서에서 셰이프 복사 및 붙여넣기 | Microsoft Docs"
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
  - "셰이프[Visual Studio에서 Office 개발], Visio 셰이프 복사 및 붙여넣기"
  - "Visio[Visual Studio에서 Office 개발], Visio 셰이프 복사 및 붙여넣기"
ms.assetid: 762d95cf-2d5c-4dea-988b-8f4da88fa1f1
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 프로그래밍 방식으로 Visio 문서에서 셰이프 복사 및 붙여넣기
  문서 한 페이지의 셰이프를 프로그래밍 방식으로 복사하고 동일한 문서의 새 페이지에 붙여넣을 수 있습니다. 기본 위치\(활성 창의 가운데\)에 붙여넣을 수도 있고 아니면 원래 페이지의 동일한 좌표 위치에 붙여넣을 수도 있습니다.  
  
## 셰이프 복사 및 붙여넣기  
 개체 모델에 대한 세부 정보는 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](HV10070304), [Microsoft.Office.Interop.Visio.Shape.DrawOval](HV10070300), [Microsoft.Office.Interop.Visio.Shape.Copy](HV10070291), [Microsoft.Office.Interop.Visio.Shape.Paste](HV10070437) 메서드 및 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](HV10071835) 플래그를 참조하세요.  
  
#### 셰이프를 다른 페이지의 가운데에 복사하려면  
  
-   다음 예제에서는 첫 번째 페이지에서 셰이프를 복사하여 두 번째 페이지의 가운데에 붙여넣는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#14)]  
  
## 동일한 위치를 사용하여 셰이프 복사 및 붙여넣기  
 개체 모델에 대한 세부 정보는 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](HV10070304), [Microsoft.Office.Interop.Visio.Shape.DrawOval](HV10070300), [Microsoft.Office.Interop.Visio.Shape.Copy](HV10070291), [Microsoft.Office.Interop.Visio.Shape.Paste](HV10070437) 메서드 및 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](HV10071835) 플래그를 참조하세요.  
  
 붙여넣은 정보의 형식을 제어하고 선택적으로 원본 파일\(예: Microsoft Office Word 문서\)에 연결해야 하는 경우 PasteSpecial 메서드를 사용합니다.  
  
#### 셰이프 및 셰이프 위치를 다른 페이지에 복사하려면  
  
-   다음 예제에서는 첫 번째 페이지에서 셰이프를 복사하고 원래 좌표 위치를 사용하여 두 번째 페이지에 붙여넣는 방법을 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#15)]  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [Visio 셰이프 작업](../vsto/working-with-visio-shapes.md)   
 [방법: 프로그래밍 방식으로 Visio 문서에 셰이프 추가](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  