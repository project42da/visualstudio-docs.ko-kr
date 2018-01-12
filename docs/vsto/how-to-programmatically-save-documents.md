---
title: "방법: 프로그래밍 방식으로 문서를 저장할 | Microsoft Docs"
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
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 68bf8450906dae3faf5f62acd2d057718938b520
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-save-documents"></a>방법: 프로그래밍 방식으로 문서 저장
  Microsoft Office Word 문서를 저장 하는 방법은 여러 가지가 있습니다. 문서 이름을 변경 하지 않고 문서를 저장할 수 또는 새 이름으로 문서를 저장할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="saving-a-document-without-changing-the-name"></a>이름을 변경 하지 않고 문서 저장  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정과 관련 된 문서를 저장 하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 메서드를 호출합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]  
  
#### <a name="to-save-the-active-document"></a>활성 문서를 저장 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Interop.Word._Document.Save%2A> 활성 문서에 대 한 메서드. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
     [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]  
  
 저장할 문서 현재 문서 인지 확실 하지 않은 이름을 사용 하 여를 참조할 수 있습니다.  
  
#### <a name="to-save-a-document-specified-by-name"></a>이름으로 지정 된 문서를 저장 하려면  
  
1.  에 대 한 인수로 문서 이름을 사용 하 여는 <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션입니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]  
  
## <a name="saving-a-document-with-a-new-name"></a>새 이름으로 문서 저장  
 SaveAs 메서드를 사용 하 여 새 이름으로 문서를 저장 합니다. 이 방법을 사용 하 여 수는 <xref:Microsoft.Office.Tools.Word.Document> 또는 네이티브는 문서 수준 Word 프로젝트에서 호스트 항목 <xref:Microsoft.Office.Interop.Word.Document> 모든 Word 프로젝트의 개체입니다. 이 메서드는 새 파일 이름을 지정 하지 않지만 다른 인수는 선택 사항 필요 합니다.  
  
> [!NOTE]  
>  표시 하는 경우는 **SaveAs** 내에 대화 상자는 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 의 이벤트 처리기 `ThisDocument` 설정 하 고는 *취소* 매개 변수를 **false**, 응용 프로그램 수 예기치 않게 종료. 설정 하는 경우는 *취소* 매개 변수를 **true**, 자동 저장 비활성화 되었음을 나타내는 오류 메시지가 나타납니다.  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>새 이름으로 문서 수준 사용자 지정과 관련 된 문서를 저장 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 의 메서드는 `ThisDocument` 정규화 된 경로 파일 이름을 사용 하 여 프로젝트의 클래스입니다. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다. 이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 대상 디렉터리가 존재 하지 않는 경우 또는 파일을 저장 하는 다른 문제가 있는 경우 메서드에서 예외를 throw 합니다. 사용 하는 것이 좋습니다는 **try … catch** 주위 차단는 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드 또는 메서드 내에서 호출 합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]  
  
#### <a name="to-save-a-native-document-with-a-new-name"></a>기본 문서를 새 이름으로 저장 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Document> 정규화 된 경로 파일 이름을 사용 하 여를 저장 하려는 합니다. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다.  
  
     다음 코드 예제에서는 새 이름으로 활성 문서를 저장합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 대상 디렉터리가 존재 하지 않는 경우 또는 파일을 저장 하는 다른 문제가 있는 경우 메서드에서 예외를 throw 합니다. 사용 하는 것이 좋습니다는 **try … catch** 주위 차단는 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드 또는 메서드 내에서 호출 합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   C 드라이브에 Test 라는 디렉터리에 존재 해야 NewDocument.doc 라는 이름으로 문서를 저장 하려면  
  
-   C 드라이브에 존재 해야 Test 라는 디렉터리를 새 이름으로 문서를 저장 하려면  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)   
 [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  