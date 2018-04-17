---
title: '방법: 프로그래밍 방식으로 숨김된 모드에서 Word 대화 상자를 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7b9d9b49783e3070e91291460e3f4aa7a4667620
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>방법: 프로그래밍 방식으로 숨김 모드에서 Word 대화 상자 사용
  사용자에 게 표시 하지 않고 Microsoft Office Word의 기본 제공 대화 상자를 호출 하 여 호출 하 여 복잡 한 작업을 수행할 수 있습니다. 사용 하 여이 작업을 수행할 수는 <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Dialog> 호출 하지 않고 개체는 <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> 메서드.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="examples"></a>예제  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다는 **페이지 설정** 사용자 입력 없음 된 다중 페이지 설정 속성을 설정 하는 숨김된 모드에서 대화 상자. 예제에서는 사용는 <xref:Microsoft.Office.Interop.Word.Dialog> 지정 페이지 크기를 구성 하는 개체입니다. 이런 식으로, 아래쪽 여백, 위쪽 여백 등 페이지 설정에 대 한 특정 설정이의 런타임에 바인딩된 속성으로 사용할 수는 <xref:Microsoft.Office.Interop.Word.Dialog> 개체입니다. 이러한 속성 런타임에 Word에서 동적으로 생성 됩니다.  
  
 다음 예제에서는 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다 여기서 **Option Strict** 전원이 꺼져 Visual C# 프로젝트에서 대상으로 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]합니다. 이러한 프로젝트에서는 Visual Basic 및 Visual C# 컴파일러에서 런타임에 바인딩 기능을 사용할 수 있습니다. 이 예제를 사용 하려면에서 실행 된 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]  
  
 다음 예제에서는 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 여기서 **Option Strict** 켜져 있습니다. 이러한 프로젝트 해야 리플렉션을 사용 하 여 런타임에 바인딩된 속성에 액세스 합니다. 이 예제를 사용 하려면에서 실행 된 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 Word에서 기본 제공 대화 상자를 사용 하 여](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)   
 [리플렉션(C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [리플렉션(Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  