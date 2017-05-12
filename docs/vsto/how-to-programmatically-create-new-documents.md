---
title: "방법: 프로그래밍 방식으로 새 문서 만들기"
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
  - "문서[Visual Studio에서 Office 개발], 만들기"
  - "템플릿[Visual Studio에서 Office 개발], 사용자 지정 문서"
  - "Word[Visual Studio에서 Office 개발], 문서 만들기"
ms.assetid: c24bb8a3-1303-438e-9b33-ba8b00b29c3b
caps.latest.revision: 49
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 48
---
# 방법: 프로그래밍 방식으로 새 문서 만들기
  프로그래밍 방식으로 문서를 만드는 경우 새 문서는 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 개체입니다.  이 개체에는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목의 추가 이벤트 및 데이터 바인딩 기능이 없습니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하세요.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 문서 수준 프로젝트를 개발하는 경우 프로그래밍 방식으로 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목을 프로젝트에 추가할 수 없습니다.  VSTO 추가 기능 프로젝트에서 런타임에 <xref:Microsoft.Office.Interop.Word.Document> 개체를 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목으로 변환할 수 있습니다.  자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
### 기본 서식 파일을 기반으로 하여 새 문서를 만들려면  
  
-   <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드를 사용하여 기본 서식 파일을 기반으로 하는 새 문서를 만듭니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreWordAutomation#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#1)]  
  
## 사용자 지정 서식 파일 사용  
 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드에는 기본 서식 파일 이외의 서식 파일을 기반으로 하여 새 문서를 만들기 위한 선택적 *Template* 인수가 있습니다.  서식 파일의 파일 이름 및 정규화된 경로를 제공해야 합니다.  
  
#### 사용자 지정 서식 파일을 기반으로 하여 새 문서를 만들려면  
  
-   <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드를 호출하고 서식 파일의 경로를 지정합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreWordAutomation#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#2)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  