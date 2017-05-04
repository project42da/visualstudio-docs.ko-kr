---
title: "방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입 | Microsoft Docs"
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
  - "범위, 문서에 텍스트 삽입"
  - "텍스트[Visual Studio에서 Office 개발], 문서에 삽입"
  - "범위, 문서에서 텍스트 바꾸기"
  - "문서[Visual Studio에서 Office 개발], 텍스트 삽입"
  - "텍스트[Visual Studio에서 Office 개발], 바꾸기"
ms.assetid: 405d7442-8ba3-4fcc-b17e-7b289ffd3967
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입
  Microsoft Office Word 문서에 텍스트를 삽입하는 기본 방법에는 다음 세 가지가 있습니다.  
  
-   범위에 텍스트를 삽입합니다.  
  
-   범위의 텍스트를 새 텍스트로 바꿉니다.  
  
-   <xref:Microsoft.Office.Interop.Word.Selection> 개체의 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> 메서드를 사용하여 커서 또는 선택 영역에 텍스트를 삽입합니다.  
  
> [!NOTE]  
>  콘텐츠 컨트롤 및 책갈피에 텍스트를 삽입할 수도 있습니다. 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md) 및 [책갈피 컨트롤](../vsto/bookmark-control.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 범위에 텍스트 삽입  
 <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Text%2A> 속성을 사용하여 문서에 텍스트를 삽입합니다.  
  
#### 범위에 텍스트를 삽입하려면  
  
1.  문서의 시작 부분에 범위를 지정하고 **New Text** 텍스트를 삽입합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#51](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#51)]
     [!code-vb[Trin_VstcoreWordAutomation#51](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#51)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 코드에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#51](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#51)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#51](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#51)]  
  
2.  1자에서 삽입된 텍스트의 길이까지 확장된 <xref:Microsoft.Office.Interop.Word.Range> 개체를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#52](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#52)]
     [!code-vb[Trin_VstcoreWordAutomation#52](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#52)]  
  
## 범위에서 텍스트 바꾸기  
 지정된 범위에 텍스트가 포함되어 있는 경우 범위에 있는 모든 텍스트가 삽입된 텍스트로 바뀝니다.  
  
#### 범위의 텍스트를 바꾸려면  
  
1.  문서의 처음 12자로 구성된 <xref:Microsoft.Office.Interop.Word.Range> 개체를 만듭니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#53](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#53)]
     [!code-vb[Trin_VstcoreWordAutomation#53](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#53)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 코드에서는 활성 문서를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#53](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#53)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#53](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#53)]  
  
2.  이러한 문자를 **New Text** 문자열로 바꿉니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#54](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#54)]
     [!code-vb[Trin_VstcoreWordAutomation#54](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#54)]  
  
3.  범위를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#55](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#55)]
     [!code-vb[Trin_VstcoreWordAutomation#55](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#55)]  
  
## TypeText를 사용하여 텍스트 삽입  
 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> 메서드는 선택 영역에 텍스트를 삽입합니다.<xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>는 사용자 컴퓨터에 설정된 옵션에 따라 다르게 동작합니다. 다음 프로시저의 코드에서는 <xref:Microsoft.Office.Interop.Word.Selection> 개체 변수를 선언하고 **Overtype** 옵션이 설정된 경우 해제합니다.**Overtype** 옵션이 활성화된 경우 커서 옆에 있는 텍스트를 모두 덮어씁니다.  
  
#### TypeText 메서드를 사용하여 텍스트를 삽입하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Selection> 개체 변수를 선언합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#57](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#57)]
     [!code-vb[Trin_VstcoreWordAutomation#57](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#57)]  
  
2.  **Overtype** 옵션이 설정된 경우 해제합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#58](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#58)]
     [!code-vb[Trin_VstcoreWordAutomation#58](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#58)]  
  
3.  현재 선택 영역이 삽입 지점인지 테스트합니다.  
  
     삽입 지점이면 코드가 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>를 사용하여 문장을 삽입하고 <xref:Microsoft.Office.Interop.Word.Selection.TypeParagraph%2A> 메서드를 사용하여 단락 표시를 삽입합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#59](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#59)]
     [!code-vb[Trin_VstcoreWordAutomation#59](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#59)]  
  
4.  **ElseIf** 블록의 코드에서는 선택이 일반 선택인지 테스트합니다. 일반 선택이면 다른 **If** 블록에서 **ReplaceSelection** 옵션이 설정되었는지 테스트합니다. 일반 선택이면 코드에서 선택 영역의 <xref:Microsoft.Office.Interop.Word.Selection.Collapse%2A> 메서드를 사용하여 선택 영역을 선택한 텍스트 블록의 시작 부분에 있는 삽입 지점으로 축소합니다. 텍스트와 단락 표시를 삽입합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#60](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#60)]
     [!code-vb[Trin_VstcoreWordAutomation#60](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#60)]  
  
5.  선택 영역이 삽입 지점 또는 선택한 텍스트 블록이 아니면 **Else** 블록의 코드에서 아무 작업도 수행하지 않습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#61](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#61)]
     [!code-vb[Trin_VstcoreWordAutomation#61](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#61)]  
  
 키보드에 있는 백스페이스 키의 기능과 유사한 <xref:Microsoft.Office.Interop.Word.Selection> 개체의 <xref:Microsoft.Office.Interop.Word.Selection.TypeBackspace%2A> 메서드를 사용할 수도 있습니다. 그러나 텍스트 삽입 및 조작의 경우 <xref:Microsoft.Office.Interop.Word.Range> 개체가 더 많은 제어를 제공합니다.  
  
 다음 예제에서는 전체 코드를 보여 줍니다. 이 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 코드를 실행합니다.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#56](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#56)]
 [!code-vb[Trin_VstcoreWordAutomation#56](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#56)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서의 텍스트 서식 지정](../vsto/how-to-programmatically-format-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)  
  
  