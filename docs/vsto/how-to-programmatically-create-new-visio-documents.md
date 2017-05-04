---
title: "방법: 프로그래밍 방식으로 새 Visio 문서 만들기 | Microsoft Docs"
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
  - "Visio[Visual Studio에서 Office 개발], Visio 문서 만들기"
  - "문서[Visual Studio에서 Office 개발], Visio 문서 만들기"
ms.assetid: a0294d4c-be49-4cd0-b22e-3ec7568f3ec7
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 프로그래밍 방식으로 새 Visio 문서 만들기
  새 Microsoft Office Visio 드로잉 문서를 만들려면 열려 있는 Visio 문서의 Microsoft.Office.Interop.Visio.Documents 컬렉션에 추가합니다. 결과적으로 Microsoft.Office.Interop.Visio.Documents.Add 메서드는 새 Visio 드로잉 문서를 만듭니다. 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Documents.Add](HV10069241) 메서드를 참조하세요.  
  
## 비어 있는 새 문서 만들기  
  
#### 새 문서를 만들려면  
  
-   템플릿을 기반으로 하지 않는 빈 문서를 새로 만들려면 Microsoft.Office.Interop.Visio.Documents.Add 메서드를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#1)]  
  
## 기존 문서에서 복사된 문서 만들기  
 Microsoft.Office.Interop.Visio.Documents.Add 메서드를 사용하면 기존 Visio 문서의 복사본인 새 문서를 만들 수 있습니다. 다이어그램의 파일 이름 및 정규화된 경로를 제공해야 합니다.  
  
#### 기존 문서에서 복사된 새 문서를 만들려면  
  
-   Microsoft.Office.Interop.Visio.Documents.Add 메서드를 호출하고 Visio 다이어그램의 경로를 지정합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#2)]  
  
## 기존 스텐실에서 복사된 스텐실 만들기  
 [Microsoft.Office.Interop.Visio.Documents.Add](HV10069241) 메서드는 기존 Visio 스텐실의 복사본인 새 스텐실을 만들 수 있습니다. 스텐실의 파일 이름 및 정규화된 경로를 제공해야 합니다.  
  
#### 기존 스텐실에서 복사된 새 스텐실을 만들려면  
  
-   Microsoft.Office.Interop.Visio.Documents.Add 메서드를 호출하고 스텐실의 경로를 지정합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#3)]  
  
## 기존 템플릿을 기반으로 문서 만들기  
 Microsoft.Office.Interop.Visio.Documents.Add 메서드는 기존 Visio 템플릿\(.vst 파일\)을 기반으로 하는 새 문서\(.vsd 파일\)를 만들 수 있습니다. 이 메서드는 템플릿 작업 영역의 일부인 스텐실, 스타일 및 설정을 복사합니다. 서식 파일의 파일 이름 및 정규화된 경로를 제공해야 합니다.  
  
#### 기존 템플릿을 기반으로 새 문서를 만들려면  
  
-   Microsoft.Office.Interop.Visio.Documents.Add 메서드를 호출하고 템플릿의 경로를 지정합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/CS/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreVisioAutomationAddIn/VB/ThisAddIn.vb#4)]  
  
## 코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   이름이 `myDrawing.vsd`인 Visio 문서가 내 문서 폴더\(Windows XP 및 이전\) 또는 문서 폴더\(Windows Vista\)의 `Test` 디렉터리에 있어야 합니다.  
  
-   이름이 `myStencil.vss`인 Visio 문서가 내 문서 폴더\(Windows XP 및 이전\) 또는 문서 폴더\(Windows Vista\)의 `Test` 디렉터리에 있어야 합니다.  
  
-   이름이 `myTemplate.vst`인 Visio 문서가 내 문서 폴더\(Windows XP 및 이전\) 또는 문서 폴더\(Windows Vista\)의 `Test` 디렉터리에 있어야 합니다.  
  
## 참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 열기](../vsto/how-to-programmatically-open-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  