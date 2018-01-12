---
title: "연습: Word 작업 창의 컨트롤에 데이터 바인딩 | Microsoft Docs"
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
- controls [Office development in Visual Studio], data binding
- actions panes [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], smart documents
- data binding [Office development in Visual Studio], actions panes
- actions panes [Office development in Visual Studio], binding controls
- smart documents [Office development in Visual Studio], data binding
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c53c8ba65c07f2c488f33835cb045524069e3285
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-binding-data-to-controls-on-a-word-actions-pane"></a>연습: Word 작업 창의 컨트롤에 데이터 바인딩
  이 연습에서는 Word에서 작업 창의 컨트롤에 데이터 바인딩. 컨트롤은 SQL Server 데이터베이스의 테이블 간 마스터/세부 관계를 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   데이터에 바인딩되는 Windows Forms 컨트롤을 사용 하 여 작업 창 만들기  
  
-   마스터/세부 관계를 사용 하 여 컨트롤에 데이터를 표시 합니다.  
  
-   응용 프로그램을 열 때 작업 창을 표시 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
-   Northwind SQL Server 예제 데이터베이스를 사용 하 여 서버에 액세스 합니다.  
  
-   사용 권한에서 읽기 / 쓰기를 SQL Server 데이터베이스입니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름으로 한 Word 문서 프로젝트 만들기 **My Word 작업 창의**합니다. 마법사에서 선택 **새 문서**합니다.  
  
     자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio 디자이너에서 새 Word 문서가 열리고 추가 **My Word 작업 창의** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-controls-to-the-actions-pane"></a>작업 창에 컨트롤 추가  
 이 연습에서는 데이터 바인딩된 Windows Forms 컨트롤을 포함 하는 작업 창 컨트롤이 필요 합니다. 데이터 원본을 프로젝트에 추가 하 고 컨트롤을 끌어서는 **데이터 소스** 작업 창 컨트롤에는 창입니다.  
  
#### <a name="to-add-an-actions-pane-control"></a>작업 창 컨트롤을 추가 하려면  
  
1.  선택 된 **My Word 작업 창의** 프로젝트에서 **솔루션 탐색기**합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**, 이름을 **actionscontrol로 지정한**, 클릭 하 고 **추가**합니다.  
  
#### <a name="to-add-a-data-source-to-the-project"></a>데이터 원본을 프로젝트에 추가 하려면  
  
1.  **데이터 소스** 창이 표시되지 않으면 메뉴 모음에서 **보기**, **다른 창**, **데이터 소스**를 차례로 선택하여 이를 표시합니다.  
  
    > [!NOTE]  
    >  경우 **데이터 소스 표시** 를 사용할 수 없으면 Word 문서를 클릭 한 다음 다시 확인 합니다.  
  
2.  클릭 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
3.  선택 **데이터베이스** 클릭 하 고 **다음**합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 데이터 연결을 선택 하거나 새 연결을 사용 하 여 추가 된 **새 연결** 단추입니다.  
  
5.  **다음**을 클릭합니다.  
  
6.  옵션을 선택 하는 경우 연결을 저장 하 고 클릭 한 다음의 선택을 취소 **다음**합니다.  
  
7.  확장 된 **테이블** 에서 노드는 **데이터베이스 개체** 창.  
  
8.  옆에 확인란을 선택 된 **Suppliers** 및 **제품** 테이블입니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에서 추가 **Suppliers** 테이블 및 **제품** 테이블는 **데이터 소스** 창. 또한 형식화 된 데이터 집합에 표시 되는 프로젝트에 추가 **솔루션 탐색기**합니다.  
  
#### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤을 추가 하려면  
  
1.  에 **데이터 원본** 창 확장는 **Suppliers** 테이블입니다.  
  
2.  드롭다운 화살표를 클릭는 **회사 이름** 노드를 선택한 **ComboBox**합니다.  
  
3.  끌기 **CompanyName** 에서 **데이터 소스** 작업 창 컨트롤에는 창입니다.  
  
     A <xref:System.Windows.Forms.ComboBox> 작업 창 컨트롤에 컨트롤이 만들어집니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `SuppliersBindingSource`, 테이블 어댑터 및 <xref:System.Data.DataSet> 구성 요소 트레이에 프로젝트에 추가 됩니다.  
  
4.  선택 `SuppliersBindingNavigator` 에 **구성 요소** 트레이 하 고 DELETE 키를 누릅니다. 사용 하지 것입니다는 `SuppliersBindingNavigator` 이 연습에서 합니다.  
  
    > [!NOTE]  
    >  삭제 된 `SuppliersBindingNavigator` 것에 대해 생성 된 코드를 모두 제거 하지 않습니다. 이 코드를 제거할 수 있습니다.  
  
5.  콤보 상자를 이동 하 여 레이블 옮기고 변경 되도록는 **크기** 속성을 **171, 21**합니다.  
  
6.  에 **데이터 원본** 창 확장는 **제품** 의 자식 테이블에는 **Suppliers** 테이블입니다.  
  
7.  드롭다운 화살표를 클릭는 **ProductName** 노드를 선택한 **ListBox**합니다.  
  
8.  끌기 **ProductName** 작업 창 컨트롤입니다.  
  
     A <xref:System.Windows.Forms.ListBox> 작업 창 컨트롤에 컨트롤이 만들어집니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `ProductBindingSource` 테이블 어댑터 구성 요소 트레이에 프로젝트에 추가 됩니다.  
  
9. 목록 상자를 이동 하 여 레이블 옮기고 변경 되도록는 **크기** 속성을 **171, 95**합니다.  
  
10. 끌어서는 <xref:System.Windows.Forms.Button> 에서 **도구 상자** 작업 창으로 제어 하 고 목록 상자 아래에 놓습니다.  
  
11. 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.Button>, 클릭 **속성** 바로 가기 메뉴에서 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**삽입**|  
    |**텍스트**|**삽입**|  
  
12. 컨트롤에 맞게 사용자 정의 컨트롤의 크기를 조정 합니다.  
  
## <a name="setting-up-the-data-source"></a>데이터 소스를 설정합니다.  
 데이터 소스를 설정 하려면 코드를 추가 하는 <xref:System.Windows.Forms.UserControl.Load> 컨트롤의 데이터로 채우는 작업 창 컨트롤의 이벤트는 <xref:System.Data.DataTable>를 설정 하 고는 <xref:System.Windows.Forms.Binding.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 각 컨트롤에 대 한 속성.  
  
#### <a name="to-load-the-control-with-data"></a>컨트롤에 데이터를 로드 하지  
  
1.  에 <xref:System.Windows.Forms.UserControl.Load> 의 이벤트 처리기는 `ActionsControl` 클래스, 다음 코드를 추가 합니다.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#1)]  
  
2.  C#에서 이벤트 처리기를 연결 해야는 <xref:System.Windows.Forms.UserControl.Load> 이벤트입니다. 이 코드를 배치할 수 있습니다는 `ActionsControl` 생성자를 호출한 후 `InitializeComponent`합니다. 이벤트 처리기를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#33](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#33)]  
  
#### <a name="to-set-data-binding-properties-of-the-controls"></a>컨트롤의 데이터 바인딩 속성을 설정 하려면  
  
1.  `CompanyNameComboBox` 컨트롤을 선택합니다.  
  
2.  에 **속성** 창 오른쪽의 단추를 클릭는 **DataSource** 속성과 선택 **suppliersBindingSource**합니다.  
  
3.  오른쪽의 단추를 클릭는 **DisplayMember** 속성과 선택 **CompanyName**합니다.  
  
4.  확장는 **데이터 바인딩** 속성 오른쪽의 단추를 클릭는 **텍스트** 속성과 선택 **없음**합니다.  
  
5.  `ProductNameListBox` 컨트롤을 선택합니다.  
  
6.  에 **속성** 창 오른쪽의 단추를 클릭는 **DataSource** 속성과 선택 **productsBindingSource**합니다.  
  
7.  오른쪽의 단추를 클릭는 **DisplayMember** 속성과 선택 **ProductName**합니다.  
  
8.  확장는 **데이터 바인딩** 속성 오른쪽의 단추를 클릭는 **SelectedValue** 속성과 선택 **없음**합니다.  
  
## <a name="adding-a-method-to-insert-data-into-a-table"></a>테이블에 데이터 삽입에 메서드 추가  
 다음 작업은 바인딩된 컨트롤에서 데이터를 읽고 Word 문서에서 테이블을 채웁니다. 첫째, 테이블의 머리글의 서식을 지정 하기 위한 프로시저를 만들고 추가 `AddData` 메서드를 만들고 Word 표를 포맷 합니다.  
  
#### <a name="to-format-the-table-headings"></a>테이블 머리글의 서식을 지정 하려면  
  
1.  에 `ActionsControl` 클래스, 테이블의 머리글의 서식을 지정 하려면 메서드를 만듭니다.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#2)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#2)]  
  
#### <a name="to-create-the-table"></a>테이블을 만들려면  
  
1.  에 `ActionsControl` 클래스, 하나는 아직 존재 하며, 작업 창에서 테이블에 데이터를 추가 하는 경우는 테이블을 만듭니다는 메서드를 작성 합니다.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#3)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#3)]  
  
#### <a name="to-insert-text-into-a-word-table"></a>텍스트를 Word 표를 삽입 하려면  
  
1.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 의 이벤트 처리기는 **삽입** 단추입니다.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#4)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#4)]  
  
2.  C#에서 이벤트 처리기를 만들어야 합니다는 <xref:System.Windows.Forms.Control.Click> 단추의 이벤트가 있습니다.  이 코드를 배치할 수 있습니다는 <xref:System.Windows.Forms.UserControl.Load> 의 이벤트 처리기는 `ActionsControl` 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#5)]  
  
## <a name="showing-the-actions-pane"></a>작업 창 표시  
 작업 창 컨트롤에 추가 된 후 표시 됩니다.  
  
#### <a name="to-show-the-actions-pane"></a>작업 창을 표시 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **ThisDocument.vb** 또는 **ThisDocument.cs**, 클릭 하 고 **코드 보기** 바로 가기 메뉴.  
  
2.  맨 위에 있는 컨트롤의 새 인스턴스를 만들고는 `ThisDocument` 다음 예제와 같이 않도록 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#6)]
     [!code-vb[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#6)]  
  
3.  코드를 추가 하는 <xref:Microsoft.Office.Tools.Word.Document.Startup> 의 이벤트 처리기 `ThisDocument` 다음 예제와 같이 되도록 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 문서를 열 때 작업 창이 표시 되는지 확인 하려면 문서를 테스트할 수 있습니다. 작업 창의 컨트롤에서 마스터/세부 관계를 테스트 하 고 채워지는지 데이터는 Word에서 확인 하면 테이블의 **삽입** 단추를 클릭 합니다.  
  
#### <a name="to-test-your-document"></a>문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  작업 창이 표시 되는지 확인 합니다.  
  
3.  콤보 상자에 회사를 선택 하 고 확인 하는 항목에는 **제품** 목록 상자의 변경 합니다.  
  
4.  제품을 클릭 하 여 **삽입** 작업 창에서 제품 세부 정보는 Word에서 테이블에 추가 되었는지 확인 하 고 있습니다.  
  
5.  다양 한 회사의 다른 제품을 삽입 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 Word에서 작업 창의 컨트롤에 데이터를 바인딩하는 기본적인 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   Excel에서 컨트롤의 데이터 바인딩 자세한 내용은 참조 [연습: Excel 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)합니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  