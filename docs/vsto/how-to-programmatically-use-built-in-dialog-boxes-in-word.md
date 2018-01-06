---
title: "방법: 프로그래밍 방식으로 Word에서 기본 제공 대화 상자를 사용 하 여 | Microsoft Docs"
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
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
ms.assetid: 0c7e4338-dead-4444-868b-3b0212368455
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 25353b95a997380ea682059a43494cc2a977f943
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>방법: 프로그래밍 방식으로 Word의 기본 제공 대화 상자 사용
  Microsoft Office Word를 사용할 때 사용자 입력에 대 한 대화 상자를 표시 하는 경우가 있습니다. 만들 수 있지만 사용자 고유의 수도 있습니다에 노출 되는 word에서 기본 제공 대화 상자를 사용 하 여 접근 방식을 <xref:Microsoft.Office.Interop.Word.Dialogs> 의 컬렉션은 <xref:Microsoft.Office.Interop.Word.Application> 개체입니다. 이 열거형으로 표시 되는 기본 제공 대화 상자에서는 200 이상의 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="displaying-dialog-boxes"></a>대화 상자 표시  
 대화 상자를 표시 하려면 값 중 하나를 사용는 <xref:Microsoft.Office.Interop.Word.WdWordDialog> 열거를 만드는 한 <xref:Microsoft.Office.Interop.Word.Dialog> 표시 하려면 대화 상자를 나타내는 개체입니다. 그런 다음 호출에서 <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Dialog> 개체입니다.  
  
 다음 코드 예제에서는 표시 하는 방법을 보여 줍니다.는 **파일 열기** 대화 상자. 이 예제를 사용 하려면에서 실행 된 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]  
  
### <a name="accessing-dialog-box-members-that-are-available-through-late-binding"></a>런타임에 바인딩을 통해 사용할 수 있는 대화 상자 멤버 액세스  
 일부 속성 및 Word에서 대화 상자의 메서드는 런타임에 바인딩을 통해서만 사용할 수 있습니다. 프로젝트나 Visual Basic에서는 **Option Strict** 켜져, 리플렉션을 사용 하 여 이러한 멤버에 액세스 해야 합니다. 자세한 내용은 [Late Binding in Office Solutions](../vsto/late-binding-in-office-solutions.md)을 참조하세요.  
  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다.는 **이름** 의 속성은 **파일 열기** 프로젝트나 Visual Basic의 대화 상자 **Option Strict** 는 꺼져 있거나 Visual C#에서 프로젝트 대상으로 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]합니다. 이 예제를 사용 하려면에서 실행 된 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 다음 코드 예제에서는 리플렉션을 사용 하 여 액세스 하는 방법을 보여 줍니다.는 **이름** 의 속성은 **파일 열기** 프로젝트나 Visual Basic의 대화 상자 **Option Strict** 은 켜 집니다. 이 예제를 사용 하려면에서 실행 된 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 숨김된 모드에서 Word 대화 상자를 사용 하 여](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [Option Strict 문](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [리플렉션(C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [리플렉션(Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  