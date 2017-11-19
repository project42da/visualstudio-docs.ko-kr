---
title: "방법: 프로그래밍 방식으로 시작 및 끝 문자 범위를 검색 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
ms.assetid: 734c630c-abc9-491d-94b6-429d1fc7a4cc
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e0cec972c731c823bb8c41f133ac721233a1b028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색
  이 예제는 범위의 시작 및 끝 위치의 문자 위치를 가져오는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 범위의 시작 및 끝 글자를 가져오려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 개체의 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 및 <xref:Microsoft.Office.Interop.Word.Range> 속성 값을 가져옵니다. 다음 코드 예제에서는 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-an-vsto-add-in"></a>VSTO 추가 기능을 사용하여 범위의 시작 및 끝 문자를 가져오려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 개체의 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 및 <xref:Microsoft.Office.Interop.Word.Range> 속성 값을 가져옵니다. 다음 코드 예제에서는 활성 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 Word에서 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 축소 범위 또는 문서 선택 영역](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시를 제외](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [방법: 프로그래밍 방식으로 문서의 문자 수 세기](../vsto/how-to-programmatically-count-characters-in-documents.md)  
  
  