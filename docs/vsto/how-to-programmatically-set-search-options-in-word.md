---
title: '방법: 프로그래밍 방식으로 Word에서 검색 옵션을 설정 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3be8d12f18e4ea0b6d05cbad92c08c7b5427315c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정
  Microsoft Office Word 문서에서 선택 항목에 대 한 검색 옵션을 설정 하는 방법은 두 가지가 있습니다.  
  
-   개별 속성을 설정는 <xref:Microsoft.Office.Interop.Word.Find> 개체입니다.  
  
-   인수를 사용 하 여는 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Find> 개체입니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-properties-of-a-find-object"></a>Find 개체의 속성을 사용 하 여  
 속성을 설정 하는 다음 코드는 <xref:Microsoft.Office.Interop.Word.Find> 현재 선택 영역 내에서 텍스트를 검색할 개체입니다. 검색 조건을 검색할 정방향, 줄 바꿈, 및 텍스트를 검색 하는 등의 속성을 가지는 <xref:Microsoft.Office.Interop.Word.Find> 개체입니다.  
  
 각 속성의 설정에서 <xref:Microsoft.Office.Interop.Word.Find> 개체에서 매개 변수로 동일한 속성을 지정 해야 하기 때문에 C# 코드를 작성 하 여 유용 하지 않습니다는 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드. 따라서이 예제에서는 Visual Basic 코드에만 포함합니다.  
  
#### <a name="to-set-search-options-using-a-find-object"></a>Find 개체를 사용 하 여 검색 옵션을 설정 하려면  
  
1.  속성을 설정는 <xref:Microsoft.Office.Interop.Word.Find> 텍스트에 대 한 선택을 통해 앞으로 검색 개체 **오세요**합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]  
  
## <a name="using-execute-method-arguments"></a>메서드 인수 Execute 사용  
 다음 코드에서는 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Find> 현재 선택 영역 내에서 텍스트를 검색할 개체입니다. 검색 조건을 검색할 정방향, 줄 바꿈, 및 텍스트를 검색 하는 등의 매개 변수로 전달 되는 공지는 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드.  
  
#### <a name="to-set-search-options-using-execute-method-arguments"></a>Execute 메서드 인수를 사용 하 여 검색 옵션을 설정 하려면  
  
1.  검색 조건을의 매개 변수로 전달 된 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 텍스트에 대 한 선택을 통해 앞으로 검색 하는 메서드 **오세요**합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 검색 하 고 문서에서 텍스트 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 반복](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  