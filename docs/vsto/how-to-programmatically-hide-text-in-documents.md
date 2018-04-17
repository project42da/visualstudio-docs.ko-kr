---
title: '방법: 프로그래밍 방식으로 문서에서 텍스트 숨기기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], hiding text
- text [Office development in Visual Studio], hiding in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b8e2ea2f5f8af3876fe64d90d5f2d77874ebb252
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-hide-text-in-documents"></a>방법: 프로그래밍 방식으로 문서에서 텍스트 숨기기
  텍스트의 특정 범위에 대해 <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> 의 <xref:Microsoft.Office.Interop.Word.Range.Font%2A> 속성을 설정하여 문서에서 텍스트를 숨길 수 있습니다.  
  
 예를 들어 문서를 프린터로 보내기 전에 <xref:Microsoft.Office.Tools.Word.Bookmark> (문서 수준 사용자 지정) 또는 <xref:Microsoft.Office.Interop.Word.Bookmark> (VSTO 추가 기능) 내에 일시적으로 텍스트를 숨길 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-hide-text-in-a-bookmark-control-while-printing-the-document"></a>문서를 인쇄하는 동안 책갈피 컨트롤에서 텍스트를 숨기려면  
  
1.  지정된 범위에 있는 모든 텍스트를 숨기는 프로시저를 만듭니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#105)]
     [!code-csharp[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#105)]  
  
2.  지정된 범위에 있는 모든 텍스트를 표시하는 프로시저를 만듭니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#106)]
     [!code-csharp[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#106)]  
  
3.  책갈피의 범위를 `HideText` 메서드로 전달하고, 문서를 인쇄한 다음 동일한 범위를 `UnhideText` 메서드로 전달합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다. 이 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#107)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다. 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#107)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드 예제에서는 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 이라는 <xref:Microsoft.Office.Interop.Word.Bookmark> 컨트롤(문서 수준 사용자 지정) 또는 `bookmark1`컨트롤(VSTO 추가 기능)이 포함된다고 가정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 문서 인쇄](../vsto/how-to-programmatically-print-documents.md)   
 [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 Word에서 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 책갈피 텍스트 업데이트](../vsto/how-to-programmatically-update-bookmark-text.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  