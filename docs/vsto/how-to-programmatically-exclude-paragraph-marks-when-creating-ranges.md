---
title: "방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시 제외"
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
  - "문서[Visual Studio에서 Office 개발], 단락 제외"
  - "범위, Word에서 단락 표시 제외"
  - "문서[Visual Studio에서 Office 개발], 단락 표시"
  - "단락, 구조 제어"
ms.assetid: 6d563834-34bd-4462-a556-4339d9277eee
caps.latest.revision: 50
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 49
---
# 방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시 제외
  단락을 기반으로 <xref:Microsoft.Office.Interop.Word.Range> 개체를 만들 때마다 단락 표시 등 인쇄할 수 없는 모든 문자가 범위에 포함됩니다. 원본 단락의 텍스트를 대상 단락에 삽입할 수 있습니다. 대상 단락을 개별 단락으로 분할하지 않으려면 먼저 원본 단락에서 단락 표시를 제거해야 합니다. 또한 단락 서식 설정 정보는 단락 표시에 저장되므로 범위를 기존 단락에 삽입할 때 서식 정보를 포함하지 않을 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 다음 예제 절차에서는 두 개의 문자열 변수를 선언하고 활성 문서에서 첫 번째와 두 번째 단락의 내용을 가져온 다음 내용을 교환합니다. 그런 다음 이 예제에서는 <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드를 사용하여 범위에서 단락 표식을 제거하고 단락 내에 텍스트를 삽입하는 방법을 보여 줍니다.  
  
### 텍스트를 삽입할 때 단락 구조를 제어하려면  
  
1.  첫 번째 단락과 두 번째 단락에 대해 두 개의 범위 변수를 만들고 <xref:Microsoft.Office.Interop.Word.Range.Text%2A> 속성을 사용하여 해당 내용을 가져옵니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#27](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#27)]
     [!code-vb[Trin_VstcoreWordAutomation#27](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#27)]  
  
     다음 코드 예제는 응용 프로그램 수준의 VSTO 추가 기능에서 사용할 수 있습니다. 이 코드에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#27](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#27](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#27)]  
  
2.  <xref:Microsoft.Office.Interop.Word.Range.Text%2A> 속성을 할당하고 두 단락 간에 텍스트를 교환합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#28](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#28)]
     [!code-vb[Trin_VstcoreWordAutomation#28](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#28)]  
  
3.  각 범위를 차례로 선택하고 결과가 메시지 상자에 표시될 때까지 일시 중지합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#29](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#29)]
     [!code-vb[Trin_VstcoreWordAutomation#29](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#29)]  
  
4.  <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드를 사용하여 단락 표식이 더 이상 `firstRange`에 포함되지 않도록 `firstRange`를 조정합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#30](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#30)]
     [!code-vb[Trin_VstcoreWordAutomation#30](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#30)]  
  
5.  첫 번째 단락에서 나머지 텍스트를 바꾸고 새 문자열을 범위의 <xref:Microsoft.Office.Interop.Word.Range.Text%2A> 속성에 할당합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#31](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#31)]
     [!code-vb[Trin_VstcoreWordAutomation#31](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#31)]  
  
6.  `secondRange`에서 단락 표시를 포함한 텍스트를 바꿉니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#32](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#32)]
     [!code-vb[Trin_VstcoreWordAutomation#32](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#32)]  
  
7.  `firstRange`를 선택하고 메시지 상자에 결과가 표시될 때까지 일시 중지한 다음 `secondRange`에 대해 같은 작업을 수행합니다.  
  
     `firstRange`가 단락 표시를 제외하도록 다시 정의되었으므로 단락의 원본 서식이 유지됩니다. 그러나 문장이 `secondRange`의 단락 표시 위에 삽입되었으므로 개별 단락이 제거됩니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#33](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#33)]
     [!code-vb[Trin_VstcoreWordAutomation#33](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#33)]  
  
     두 범위의 원래 내용이 문자열로 저장되었으므로 문서를 원래 상태로 복원할 수 있습니다.  
  
8.  한 문자 위치에 대해 <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> 메서드를 사용하여 단락 표시를 포함하도록 `firstRange`를 다시 조정합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#34](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#34)]
     [!code-vb[Trin_VstcoreWordAutomation#34](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#34)]  
  
9. `secondRange`를 삭제합니다. 이렇게 하면 단락 3이 원래 위치로 복원됩니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#35](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#35)]
     [!code-vb[Trin_VstcoreWordAutomation#35](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#35)]  
  
10. `firstRange`의 원래 단락 텍스트를 복원합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#36](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#36)]
     [!code-vb[Trin_VstcoreWordAutomation#36](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#36)]  
  
11. <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.InsertAfter%2A> 메서드를 사용하여 원래 단락 2 내용을 `firstRange` 뒤에 삽입하고 `firstRange`를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#37](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#37)]
     [!code-vb[Trin_VstcoreWordAutomation#37](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#37)]  
  
## 문서 수준 사용자 지정 예제  
  
#### 문서 수준 사용자 지정에 텍스트를 삽입할 때 단락 구조를 제어하려면  
  
1.  다음 예제에서는 문서 수준 사용자 지정의 전체 메서드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#26](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#26)]
     [!code-vb[Trin_VstcoreWordAutomation#26](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#26)]  
  
## VSTO 추가 기능 예제  
  
#### VSTO 추가 기능에서 텍스트를 삽입할 때 단락 구조를 제어하려면  
  
1.  다음 예제에서는 VSTO 추가 기능의 전체 메서드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#26](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#26](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#26)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 또는 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  