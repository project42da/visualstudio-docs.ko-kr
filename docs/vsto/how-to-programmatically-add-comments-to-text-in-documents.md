---
title: '방법: 프로그래밍 방식으로 문서의 텍스트에 메모 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- comments, adding to documents
- documents [Office development in Visual Studio], adding comments
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 752c79bf6bd586d19b9ec572d3cd643cdfd90e70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-add-comments-to-text-in-documents"></a>방법: 프로그래밍 방식으로 문서의 텍스트에 메모 추가
  문서 클래스의 주석 속성은 Microsoft Office Word 문서에서 텍스트의 범위에 메모를 추가 합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 예제에서는 문서의 첫 번째 단락에 메모를 추가합니다.  
  
### <a name="to-add-a-new-comment-to-text-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 텍스트에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> 속성의 <xref:Microsoft.Office.Tools.Word.Document.Comments%2A> 메서드를 호출하고 범위 및 메모 텍스트를 제공합니다. 다음 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#118)]  
  
### <a name="to-add-a-new-comment-to-text-in-an-vsto-add-in"></a>VSTO 추가 기능에서 텍스트에 새 메모를 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> 속성의 <xref:Microsoft.Office.Interop.Word._Document.Comments%2A> 메서드를 호출하고 범위 및 메모 텍스트를 제공합니다.  
  
     다음 코드 예제에서는 활성 문서에 메모를 추가합니다. 이 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#118)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Word에서 메모에 추가하는 사용자 이니셜을 변경하려면 <xref:Microsoft.Office.Interop.Word._Application.UserInitials%2A> 속성을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 문서에서 모든 메모 제거](../vsto/how-to-programmatically-remove-all-comments-from-documents.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)  
  
  