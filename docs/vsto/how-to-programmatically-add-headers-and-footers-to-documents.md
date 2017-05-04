---
title: "방법: 프로그래밍 방식으로 문서에 머리글 및 바닥글 추가 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 바닥글 추가"
  - "문서[Visual Studio에서 Office 개발], 머리글 추가"
  - "바닥글, 문서에 추가"
  - "머리글, Office 문서에 추가"
ms.assetid: c7a5cc8a-d8c0-48e9-81d3-108aa6bfbb74
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 프로그래밍 방식으로 문서에 머리글 및 바닥글 추가
  <xref:Microsoft.Office.Interop.Word.Section>의 <xref:Microsoft.Office.Interop.Word.Section.Headers%2A> 속성 및 <xref:Microsoft.Office.Interop.Word.Section.Footers%2A> 속성을 사용하여 문서의 머리글 및 바닥글에 텍스트를 추가할 수 있습니다.  문서의 각 섹션에는 다음 세 개의 머리글과 바닥글이 포함됩니다.  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterPrimary>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterEvenPages>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterFirstPage>  
  
 문서 수준 사용자 지정 및 VSTO 추가 기능에 대한 절차가 서로 다릅니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 문서 수준 사용자 지정  
 다음 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
#### 문서의 바닥글에 텍스트를 추가하려면  
  
1.  다음 코드 예제에서는 문서의 각 섹션에 대한 기본 바닥글에 삽입할 텍스트의 글꼴을 설정하고 바닥글에 텍스트를 삽입합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#114](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#114)]
     [!code-vb[Trin_VstcoreWordAutomation#114](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#114)]  
  
#### 문서의 머리글에 텍스트를 추가하려면  
  
1.  다음 코드 예제에서는 문서의 각 머리글에 페이지 번호를 표시할 필드를 추가하고 텍스트가 머리글 오른쪽에 정렬되도록 단락 맞춤을 설정합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#116](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#116)]
     [!code-vb[Trin_VstcoreWordAutomation#116](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#116)]  
  
## VSTO 추가 기능  
 다음 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
#### 문서의 바닥글에 텍스트를 추가하려면  
  
1.  다음 코드 예제에서는 문서의 각 섹션에 대한 기본 바닥글에 삽입할 텍스트의 글꼴을 설정하고 바닥글에 텍스트를 삽입합니다.  이 코드 예제에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#114](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#114)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#114](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#114)]  
  
#### 문서의 머리글에 텍스트를 추가하려면  
  
1.  다음 코드 예제에서는 문서의 각 머리글에 페이지 번호를 표시할 필드를 추가하고 텍스트가 머리글 오른쪽에 정렬되도록 단락 맞춤을 설정합니다.  이 코드 예제에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#116](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#116)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#116](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#116)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 새 문서 만들기](../vsto/how-to-programmatically-create-new-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)  
  
  