---
title: "방법: 프로그래밍 방식으로 그림을 추가 및 문서에 Wordart | Microsoft Docs"
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
- documents [Office development in Visual Studio], adding pictures
- Word documents, adding pictures
- Word documents, adding Word Art
- graphics, adding to Word documents
- WordArt, adding to documents
ms.assetid: 944e1858-bc7c-471f-b5e7-adf3b0fa574d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a30c865a1bee9f3e8a75d5362688f1a83baba02a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-add-pictures-and-word-art-to-documents"></a>방법: 프로그래밍 방식으로 문서에 그림 및 WordArt 추가
  디자인 타임 또는 런타임에 그림 및 그리기 개체를 문서에 추가할 수 있습니다. WordArt를 사용하면 Microsoft Office Word 문서에 장식 텍스트를 추가할 수 있습니다. 이러한 특수 텍스트 효과는 사용자 지정하고 문서에 삽입할 수 있는 그리기 개체입니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="adding-a-picture-at-design-time"></a>디자인 타임에 그림 추가  
 문서 수준 사용자 지정을 개발하는 경우 디자인 타임에 문서에 그림을 추가할 수 있습니다.  
  
#### <a name="to-add-a-picture-to-a-word-document-at-design-time"></a>디자인 타임에 Word 문서에 그림을 추가하려면  
  
1.  문서에서 그림을 삽입하려는 위치에 커서를 놓습니다.  
  
2.  클릭는 **삽입** 리본 메뉴의 탭 합니다.  
  
3.  에 **그림** 그룹에서 클릭 **그림**합니다.  
  
4.  에 **그림 삽입** 대화 상자를 삽입 하려는 그림을 찾아 클릭 **삽입**합니다.  
  
     그림이 문서의 현재 커서 위치에 추가됩니다.  
  
## <a name="adding-a-picture-at-run-time"></a>런타임에 그림 추가  
 문서의 현재 커서 위치에 그림을 삽입할 수 있습니다.  
  
#### <a name="to-add-a-picture-at-the-cursor-location"></a>커서 위치에 그림을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.InlineShapes> 컬렉션의 <xref:Microsoft.Office.Interop.Word.InlineShapes.AddPicture%2A> 메서드를 호출하고 해당 파일의 이름을 전달합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#108)]
     [!code-csharp[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#108)]  
  
## <a name="adding-wordart-at-design-time"></a>디자인 타임에 WordArt 추가  
 문서 수준 사용자 지정을 개발하는 경우 디자인 타임에 문서에 WordArt를 추가할 수 있습니다.  
  
#### <a name="to-add-wordart-to-a-word-document-at-design-time"></a>디자인 타임에 Word 문서에 WordArt를 추가하려면  
  
1.  문서에서 WordArt를 삽입하려는 위치에 커서를 놓습니다.  
  
2.  클릭는 **삽입** 리본 메뉴의 탭 합니다.  
  
3.  에 **텍스트** 그룹에서 클릭 **WordArt**, 고 WordArt 스타일을 선택 합니다.  
  
4.  텍스트 문서에 표시할를 추가 하는 **WordArt 텍스트 편집** 대화 상자와 클릭 **확인**합니다.  
  
     선택한 WordArt 스타일이 적용된 문서에 텍스트가 추가됩니다.  
  
## <a name="adding-wordart-at-run-time"></a>런타임에 WordArt 추가  
 문서의 현재 커서 위치에 WordArt를 삽입할 수 있습니다. 문서 수준 사용자 지정 및 VSTO 추가 기능에 대한 절차가 서로 다릅니다.  
  
#### <a name="to-add-wordart-at-the-cursor-location-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 커서 위치에 WordArt를 추가하려면  
  
1.  현재 커서 위치의 왼쪽 및 위쪽 위치를 가져옵니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#109)]  
  
2.  문서에서 <xref:Microsoft.Office.Interop.Word.Shapes> 개체의 <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> 메서드를 호출합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#110)]  
  
#### <a name="to-add-wordart-at-the-cursor-location-in-a-vsto-add-in"></a>VSTO 추가 기능에서 커서 위치에 WordArt를 추가하려면  
  
1.  현재 커서 위치의 왼쪽 및 위쪽 위치를 가져옵니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#109)]  
  
2.  활성 문서(또는 지정한 다른 문서)에서 <xref:Microsoft.Office.Interop.Word.Shapes> 개체의 <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> 메서드를 호출합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#110)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   라는 그림이 **SamplePicture.jpg** C 드라이브에 있어야 합니다  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [방법: 프로그래밍 방식으로 문서 저장](../vsto/how-to-programmatically-save-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  