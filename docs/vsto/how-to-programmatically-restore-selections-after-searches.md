---
title: "방법: 프로그래밍 방식으로 검색 후 선택 영역 복원 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 선택 영역 복원"
  - "검색, 검색 후 선택 영역 복원"
  - "선택 영역, 검색 후 복원"
ms.assetid: 1e6131ad-0e5b-4189-be67-5b2ed87d193d
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# 방법: 프로그래밍 방식으로 검색 후 선택 영역 복원
  문서에서 텍스트를 찾아 바꾼 경우 검색을 완료한 다음 사용자의 원래 선택 영역을 복원해야 할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 샘플 프로시저의 코드에서는 두 개의 <xref:Microsoft.Office.Interop.Word.Range> 개체를 사용합니다.  한 개체에서는 현재 <xref:Microsoft.Office.Interop.Word.Selection>을 저장하고 다른 개체에서는 검색에 사용할 범위를 문서 전체로 설정합니다.  
  
### 검색 후에 사용자의 원래 선택 영역을 복원하려면  
  
1.  문서와 현재 선택 영역에 대한 <xref:Microsoft.Office.Interop.Word.Range> 개체를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#83](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#83)]
     [!code-vb[Trin_VstcoreWordAutomation#83](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#83)]  
  
2.  검색 및 바꾸기 작업을 수행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#84](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#84)]
     [!code-vb[Trin_VstcoreWordAutomation#84](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#84)]  
  
3.  사용자의 원래 선택 영역을 복원하기 위한 시작 범위를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#85](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#85)]
     [!code-vb[Trin_VstcoreWordAutomation#85](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#85)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
## 예제  
 [!code-csharp[Trin_VstcoreWordAutomation#82](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#82)]
 [!code-vb[Trin_VstcoreWordAutomation#82](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#82)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서에서 텍스트 검색 및 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  