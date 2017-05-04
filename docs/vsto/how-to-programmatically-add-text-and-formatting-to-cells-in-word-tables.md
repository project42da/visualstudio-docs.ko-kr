---
title: "방법: 프로그래밍 방식으로 Word 표의 셀에 텍스트 및 서식 추가 | Microsoft Docs"
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
  - "셀, 텍스트 및 서식 추가"
  - "서식 지정[Visual Studio에서 Office 개발]"
  - "표[Visual Studio에서 Office 개발], 텍스트 및 서식 추가"
  - "텍스트[Visual Studio에서 Office 개발], Word 표에 추가"
ms.assetid: 3df6492a-dc9c-43ac-8fc3-0f944edd88b2
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# 방법: 프로그래밍 방식으로 Word 표의 셀에 텍스트 및 서식 추가
  각 테이블은 셀 컬렉션으로 이루어져 있습니다.  각 개별 <xref:Microsoft.Office.Interop.Word.Cell> 개체는 테이블의 한 셀을 나타냅니다.  테이블의 해당 위치로 각 셀을 참조합니다.  이 예제에서는 테이블의 첫 행과 첫 열에 있는 셀을 참조하고, 셀에 텍스트를 추가하고, 서식을 적용합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### 셀에 텍스트 및 서식을 추가하려면  
  
1.  테이블의 해당 위치에 따라 셀을 참조하고, 셀에 텍스트를 추가한 다음 서식을 적용합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  이 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#97](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#97)]
     [!code-vb[Trin_VstcoreWordAutomation#97](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#97)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다.  이 예제에서는 활성 문서를 사용합니다.  예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#97](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#97)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#97](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#97)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 Word 표 만들기](../vsto/how-to-programmatically-create-word-tables.md)   
 [방법: 프로그래밍 방식으로 Word 표에 행 및 열 추가](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [방법: 프로그래밍 방식으로 문서 속성을 사용하여 Word 표 채우기](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  