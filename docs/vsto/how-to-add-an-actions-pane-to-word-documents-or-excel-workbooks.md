---
title: "방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가 | Microsoft Docs"
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
- smart documents [Office development in Visual Studio], creating in Word
- smart documents [Office development in Visual Studio], adding controls
- actions panes [Office development in Visual Studio], creating in Word
- actions panes [Office development in Visual Studio], adding controls
ms.assetid: cea3c2b6-9364-4134-b812-50888ad8bd76
caps.latest.revision: "63"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ffdb997bbff96e99a456f7d4679a5da0e446ee4a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks"></a>방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가
  작업 창에 Microsoft Office Word 문서 또는 Microsoft Excel 통합 문서를 추가 하려면 먼저 Windows Forms 사용자 정의 컨트롤을 만듭니다. 그런 다음 사용자 정의 컨트롤을 추가 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 속성은 `ThisDocument.ActionsPane` 필드 (Word) 또는 `ThisWorkbook.ActionsPane` 프로젝트에서 필드 (Excel).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="creating-the-user-control"></a>사용자 정의 컨트롤 만들기  
 다음 절차에서는 Excel 프로젝트 또는 Word 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다. 또한 단추를 클릭할 때 문서 또는 통합 문서에 텍스트를 작성 하는 사용자 정의 컨트롤을 추가 합니다.  
  
#### <a name="to-create-the-user-control"></a>사용자 정의 컨트롤을 만들려면  
  
1.  Visual Studio에서 Word 또는 Excel 문서 수준 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**, 이름을 **HelloControl**를 클릭 하 고 **추가**합니다.  
  
    > [!NOTE]  
    >  추가할 수도 있습니다는 **사용자 정의 컨트롤** 항목을 프로젝트입니다. 에 의해 생성 된 클래스는 **작업 창 컨트롤** 및 **사용자 정의 컨트롤** 항목 기능적으로 동일 합니다.  
  
4.  **Windows Forms** 탭은 **도구 상자** 끌어는 **단추** 컨트롤을 컨트롤입니다.  
  
    > [!NOTE]  
    >  컨트롤 디자이너에 표시 되지 않으면, 두 번 클릭 **HelloControl** 에 **솔루션 탐색기**합니다.  
  
5.  코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 단추의 이벤트 처리기입니다. 다음 예제에서는 Microsoft Office Word 문서에 대 한 코드를 보여 줍니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#12)]
     [!code-vb[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/HelloControl.vb#12)]  
  
6.  C#에서는 단추 클릭에 대 한 이벤트 처리기를 추가 해야 합니다. 이 코드를 배치할 수 있습니다는 `HelloControl` 생성자를 호출한 후 `IntializeComponent`합니다.  
  
     이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#13)]  
  
## <a name="adding-the-user-control-to-the-actions-pane"></a>작업 창에 사용자 컨트롤 추가  
 작업창을 표시 하려면 사용자 정의 컨트롤을 추가 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 의 속성은 `ThisDocument.ActionsPane` 필드 (Word) 또는 `ThisWorkbook.ActionsPane` 필드 (Excel).  
  
#### <a name="to-add-the-user-control-to-the-actions-pane"></a>작업 창에 사용자 정의 컨트롤을 추가 하려면  
  
1.  다음 코드를 추가 하는 `ThisDocument` 또는 `ThisWorkbook` 클래스 수준 선언으로 클래스 (메서드에이 코드를 추가 않음).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#14)]
     [!code-vb[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#14)]  
  
2.  다음 코드를 추가 하는 `ThisDocument_Startup` 의 이벤트 처리기는 `ThisDocument` 클래스 또는 `ThisWorkbook_Startup` 의 이벤트 처리기는 `ThisWorkbook` 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#15)]
     [!code-vb[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#15)]  
  
## <a name="see-also"></a>참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [연습: 작업창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  