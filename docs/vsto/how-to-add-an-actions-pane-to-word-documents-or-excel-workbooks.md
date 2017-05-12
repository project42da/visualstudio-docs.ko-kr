---
title: "방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가"
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
  - "작업 창[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "작업 창[Visual Studio에서 Office 개발], Word에서 만들기"
  - "스마트 문서[Visual Studio에서 Office 개발], 컨트롤 추가"
  - "스마트 문서[Visual Studio에서 Office 개발], Word에서 만들기"
ms.assetid: cea3c2b6-9364-4134-b812-50888ad8bd76
caps.latest.revision: 63
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 62
---
# 방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가
  Microsoft Office Word 문서 또는 Microsoft Excel 통합 문서에 작업 창을 추가 하려면 먼저 Windows Forms 사용자 정의 컨트롤을 만듭니다.  그런 다음 사용자 정의 컨트롤에 추가 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 속성은 `ThisDocument.ActionsPane` 필드 \(Word\) 또는 `ThisWorkbook.ActionsPane` 프로젝트에서 필드 \(Excel\).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사용자 정의 컨트롤 만들기  
 다음은 Word 사용자 정의 컨트롤을 만드는 방법 또는 Excel 프로젝트를 보여 줍니다.  또한 단추를 클릭 하면 문서 또는 통합 문서에 텍스트를 쓰는 사용자 정의 컨트롤에 추가 합니다.  
  
#### 사용자 정의 컨트롤을 만들려면  
  
1.  Word 또는 Excel 문서 수준 프로젝트에서 Visual Studio 엽니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**을 선택하고 이름을 **HelloControl**로 지정한 다음 **추가**를 클릭합니다.  
  
    > [!NOTE]  
    >  또는 프로젝트에 **사용자 정의 컨트롤** 항목을 추가할 수도 있습니다.  **작업 창 컨트롤** 항목과 **사용자 정의 컨트롤** 항목에 의해 생성되는 클래스는 기능적으로 동일합니다.  
  
4.  **도구 상자**의 **Windows Forms** 탭에서 **Button** 컨트롤을 해당 컨트롤로 끌어 옵니다.  
  
    > [!NOTE]  
    >  디자이너에 **HelloControl** 컨트롤이 표시되어 있지 않으면 **솔루션 탐색기**에서 이 컨트롤을 두 번 클릭합니다.  
  
5.  코드에 추가 된 <xref:System.Windows.Forms.Control.Click> 단추의 이벤트 처리기입니다.  다음 예제에서는 Microsoft Office Word 문서에 대 한 코드를 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/HelloControl.cs#12)]
     [!code-vb[Trin_VstcoreActionsPaneWord#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/HelloControl.vb#12)]  
  
6.  C\#의 경우 단추 클릭에 대해 이벤트 처리기를 추가해야 합니다.  이 코드를 `HelloControl` 생성자에서 `IntializeComponent`에 대한 호출 밑에 배치할 수 있습니다.  
  
     이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/HelloControl.cs#13)]  
  
## 작업 창에 사용자 정의 창 컨트롤 추가  
 작업 창을 표시 하려면 사용자 정의 컨트롤에 추가 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 속성은 `ThisDocument.ActionsPane` 필드 \(Word\) 또는 `ThisWorkbook.ActionsPane` 필드 \(Excel\).  
  
#### 작업 창에 사용자 정의 컨트롤을 추가하려면  
  
1.  다음 코드를 추가 된 `ThisDocument` 또는 `ThisWorkbook` 클래스는 클래스 수준 선언으로 \(이 코드에 메서드를 추가 하지 않음\).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#14)]
     [!code-vb[Trin_VstcoreActionsPaneWord#14](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#14)]  
  
2.  다음 코드를 추가 `ThisDocument_Startup` 이벤트의 이벤트 처리기는 `ThisDocument` 클래스 또는 `ThisWorkbook_Startup` 이벤트의 이벤트 처리기는 `ThisWorkbook` 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#15)]
     [!code-vb[Trin_VstcoreActionsPaneWord#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#15)]  
  
## 참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  