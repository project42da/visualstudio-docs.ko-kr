---
title: "연습: 작업 창에서 문서로 텍스트 삽입 | Microsoft Docs"
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
ms.assetid: fd14c896-5737-4a20-94f7-6064b67112c5
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5ca062823968153d7c8979cb13c0e3d403237be1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-inserting-text-into-a-document-from-an-actions-pane"></a>연습: 작업 창에서 문서로 텍스트 삽입
  이 연습에서는 Microsoft Office Word 문서에서 작업 창을 만드는 방법을 보여 줍니다. 작업 창에는 입력을 수집 하 고 다음 텍스트 문서를 보냅니다는 두 개의 컨트롤이 포함 됩니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   작업 창 컨트롤에 Windows Forms 컨트롤을 사용 하 여 인터페이스를 디자인 합니다.  
  
-   작업 창 응용 프로그램을 열 때 표시 됩니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름으로 한 Word 문서 프로젝트 만들기 **내 기본 작업 창**합니다. 마법사에서 선택 **새 문서**합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio 디자이너에서 새 Word 문서가 열리고 추가 **내 기본 작업 창** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-text-and-bookmarks-to-the-document"></a>문서에 텍스트와 책갈피를 추가  
 작업 창에서는 텍스트 문서에서 책갈피를 보냅니다. 문서를 디자인 하려면 기본 양식을 만드는 텍스트를 입력 합니다.  
  
#### <a name="to-add-text-to-your-document"></a>텍스트 문서를 추가 하려면  
  
1.  Word 문서에 다음 텍스트를 입력 합니다.  
  
     **2008 년 3 월 21 일**  
  
     **Name**  
  
     **주소**  
  
     **이 Word에서 기본 작업 창 예제입니다.**  
  
 추가할 수 있습니다는 <xref:Microsoft.Office.Tools.Word.Bookmark> 에서 끌어 문서에 컨트롤의 **도구 상자** Visual Studio에서 또는 사용 하 여는 **책갈피** Word에서 대화 상자.  
  
#### <a name="to-add-a-bookmark-control-to-your-document"></a>문서에 책갈피 컨트롤을 추가 하려면  
  
1.  **Word 컨트롤** 탭은 **도구 상자**를 끌어 한 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서로 합니다.  
  
     **책갈피 컨트롤 추가** 대화 상자가 나타납니다.  
  
2.  단어를 선택 **이름**, 하지 않고 단락 기호를 선택 하 고 클릭 **확인**합니다.  
  
    > [!NOTE]  
    >  단락 기호 책갈피의 외부에 있어야 합니다. 단락 기호가 문서에 표시 되지 않는 경우 클릭는 **도구** 메뉴에서 **Microsoft Office Word 도구** 클릭 하 고 **옵션**합니다. 클릭는 **보기** 탭을 선택는 **단락 표시** 확인란에는 **서식 기호** 의 섹션은 **옵션** 대화 상자.  
  
3.  에 **속성** 창 변경은 **이름** 속성 **Bookmark1** 를 **showName**합니다.  
  
4.  단어를 선택 **주소**, 단락 표시를 선택 하지 않고 있습니다.  
  
5.  에 **삽입** 리본 메뉴의 탭에는 **링크** 그룹에서 클릭 **책갈피**합니다.  
  
6.  에 **책갈피** 대화 상자에서 **showAddress** 에 **책갈피 이름** 상자 한 클릭 **추가**합니다.  
  
## <a name="adding-controls-to-the-actions-pane"></a>작업 창에 컨트롤 추가  
 작업 창 인터페이스를 디자인 하려면 프로젝트에 작업 창 컨트롤을 추가 하 고 작업 창 컨트롤에 Windows Forms 컨트롤을 추가 합니다.  
  
#### <a name="to-add-an-actions-pane-control"></a>작업 창 컨트롤을 추가 하려면  
  
1.  선택 된 **내 기본 작업 창** 프로젝트에서 **솔루션 탐색기**합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  에 **새 항목 추가** 대화 상자를 클릭 **작업 창 컨트롤**, 컨트롤의 이름을 지정 **InsertTextControl,** 클릭 **추가**합니다.  
  
#### <a name="to-add-windows-form-controls-to-the-actions-pane-control"></a>Windows Form 컨트롤 작업 창 컨트롤을 추가 하려면  
  
1.  작업 창 컨트롤 디자이너에 표시 되지 않으면 두 번 클릭 **InsertTextControl**합니다.  
  
2.  **공용 컨트롤** 탭은 **도구 상자**, 끌어는 **레이블** 작업 창 컨트롤을 제어 합니다.  
  
3.  변경 된 **텍스트** 레이블 컨트롤의 속성 **이름**합니다.  
  
4.  추가 **Textbox** 작업 창 컨트롤을 제어 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**Name**|**getName**|  
    |**Size**|**130, 20**|  
  
5.  두 번째 추가 **레이블** 작업 창 컨트롤을 제어 하 고 변경 된 **텍스트** 속성을 **주소**합니다.  
  
6.  두 번째 추가 **Textbox** 작업 창 컨트롤을 제어 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**Name**|**getAddress**|  
    |**반환 허용**|**True**|  
    |**Multiline**|**True**|  
    |**Size**|**130, 40**|  
  
7.  추가 **단추** 작업 창 컨트롤을 제어 하 고 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**Name**|**addText**|  
    |**텍스트**|**삽입**|  
  
## <a name="adding-code-to-insert-text-into-the-document"></a>문서에 텍스트를 삽입 하는 코드를 추가 합니다.  
 작업 창에서 적절 한에 텍스트 상자에서 텍스트를 삽입 하는 코드를 작성 <xref:Microsoft.Office.Tools.Word.Bookmark> 문서에 컨트롤입니다. 사용할 수는 `Globals` 작업 창의 컨트롤에서 문서에 컨트롤에 액세스 하는 클래스입니다. 자세한 내용은 참조 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)합니다.  
  
#### <a name="to-insert-text-from-the-actions-pane-in-a-bookmark-in-the-document"></a>문서에서 책갈피의 작업 창에서 텍스트를 삽입 하려면  
  
1.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 의 이벤트 처리기는 **addText** 단추입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#8)]
     [!code-vb[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/InsertTextControl.vb#8)]  
  
2.  C#에서는 단추 클릭에 대 한 이벤트 처리기를 추가 해야 합니다. 이 코드를 배치할 수 있습니다는 `InsertTextControl` 생성자를 호출한 후 `IntializeComponent`합니다. 이벤트 처리기를 만드는 방법은 참조 [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#9)]  
  
## <a name="adding-code-to-show-the-actions-pane"></a>작업 창을 표시 하는 코드 추가  
 작업창을 표시 하려면 컨트롤 컬렉션에 만든 컨트롤을 추가 합니다.  
  
#### <a name="to-show-the-actions-pane"></a>작업 창을 표시 하려면  
  
1.  작업 창 컨트롤의 새 인스턴스를 만들고는 `ThisDocument` 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#10)]
     [!code-vb[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#10)]  
  
2.  다음 코드를 추가 하는 <xref:Microsoft.Office.Tools.Word.Document.Startup> 의 이벤트 처리기 `ThisDocument`합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#11)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 작업 창에서 문서를 열 때 단추를 클릭할 때 책갈피에 삽입 되는 텍스트 상자에 입력 된 텍스트가 열리는지 확인 위해 문서를 테스트 합니다.  
  
#### <a name="to-test-your-document"></a>문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  작업 창이 표시 되는지 확인 합니다.  
  
3.  작업 창에서 텍스트 상자에 이름 및 주소를 입력 하 고 클릭 **삽입**합니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   Excel에서 작업 창을 만드는 중입니다. 자세한 내용은 참조 [하는 방법: Excel 통합 문서에 작업 창 추가](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872)합니다.  
  
-   작업 창의 컨트롤에 데이터 바인딩. 자세한 내용은 참조 [연습: Word 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: Excel 통합 문서에 작업 창 추가](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Bookmark 컨트롤](../vsto/bookmark-control.md)  
  
  