---
title: "방법: 작업 창에서 컨트롤 레이아웃 관리 | Microsoft Docs"
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
  - "작업 창[Visual Studio에서 Office 개발], 컨트롤 레이아웃"
  - "컨트롤[Visual Studio에서 Office 개발], 작업 창에서 레이아웃"
  - "스마트 문서[Visual Studio에서 Office 개발], 컨트롤 레이아웃"
ms.assetid: 857550d0-b9c0-4d2f-a947-dd955bcf2823
caps.latest.revision: 59
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 55
---
# 방법: 작업 창에서 컨트롤 레이아웃 관리
  작업 창은 기본적으로 문서나 워크시트의 오른쪽에 도킹되지만 선택에 따라 왼쪽, 위쪽 또는 아래쪽에 도킹할 수도 있습니다.  여러 사용자 정의 컨트롤을 사용하는 경우 작업 창에 사용자 정의 컨트롤을 올바르게 쌓기 위한 코드를 작성할 수 있습니다.  자세한 내용은 [작업 창 개요](../vsto/actions-pane-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 컨트롤이 쌓이는 순서는 작업 창이 세로로 도킹되어 있는지 가로로 도킹되어 있는지에 따라 달라집니다.  
  
> [!NOTE]  
>  사용자가 런타임에 작업 창의 크기를 조정하는 경우 컨트롤의 크기도 작업 창과 함께 조정되도록 설정할 수 있습니다.  Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용하면 컨트롤을 작업 창에 고정할 수 있습니다.  자세한 내용은 [방법: Windows Forms에서 컨트롤 고정](../Topic/How%20to:%20Anchor%20Controls%20on%20Windows%20Forms.md)을 참조하십시오.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 작업 창 컨트롤의 스택 순서를 설정하려면  
  
1.  사용자 정의 컨트롤이나 중첩된 작업 창 컨트롤이 여러 개 있는 작업 창이 포함된 Microsoft Office Word용 문서 수준 프로젝트를 엽니다.  자세한 내용은 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)을 참조하십시오.  
  
2.  **솔루션 탐색기**에서 **ThisDocument.cs** 또는 **ThisDocument.vb**를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
3.  작업 창의 <xref:Microsoft.Office.Tools.ActionsPane.OrientationChanged> 이벤트 처리기에서 작업 창의 방향이 가로인지 확인합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#30](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#30)]
     [!code-vb[Trin_VstcoreActionsPaneWord#30](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#30)]  
  
4.  방향이 가로이면 작업 창 컨트롤이 왼쪽부터 쌓이고, 그렇지 않으면 위쪽부터 쌓입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#31](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#31)]
     [!code-vb[Trin_VstcoreActionsPaneWord#31](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#31)]  
  
5.  C\#의 경우 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트 처리기에 `ActionsPane`에 대한 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#32](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#32)]  
  
6.  프로젝트를 실행하고 작업 창이 문서의 위쪽에 도킹된 경우 작업 창 컨트롤이 왼쪽에서 오른쪽으로 쌓이는지 확인합니다. 또한 작업 창이 문서의 오른쪽에 도킹된 경우 컨트롤이 위쪽에서 아래쪽으로 쌓이는지 확인합니다.  
  
## 예제  
 [!code-csharp[Trin_VstcoreActionsPaneWord#29](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#29)]
 [!code-vb[Trin_VstcoreActionsPaneWord#29](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#29)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   사용자 정의 컨트롤이나 중첩된 작업 창 컨트롤이 여러 개 포함된 작업 창이 있는 Word 문서 수준 프로젝트가 있어야 합니다.  
  
## 참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  