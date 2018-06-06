---
title: '연습: Excel 작업 창의 컨트롤에 데이터 바인딩'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9d450a9c52ae8558167bf4cb581ce2e36f44f4e9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767912"
---
# <a name="walkthrough-bind-data-to-controls-on-an-excel-actions-pane"></a>연습: Excel 작업 창의 컨트롤에 데이터 바인딩
  이 연습에서는 Microsoft Office Excel의 작업 창에서 컨트롤에 데이터 바인딩을 보여 줍니다. 컨트롤은 SQL Server 데이터베이스의 테이블 간 마스터/세부 관계를 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   워크시트에 컨트롤을 추가 합니다.  
  
-   작업 창 컨트롤을 만듭니다.  
  
-   작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤을 추가 합니다.  
  
-   작업 창 응용 프로그램을 열 때 표시 됩니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 예제 데이터베이스를 사용 하 여 서버에 액세스 합니다.  
  
-   사용 권한에서 읽기 / 쓰기를 SQL Server 데이터베이스입니다.  
  
## <a name="create-the-project"></a>프로젝트를 만듭니다.  
 첫 번째 단계에서 Excel 통합 문서 프로젝트를 만듭니다.  
  
### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **내 Excel 작업 창의**합니다. 마법사에서 선택 **새 문서**합니다. 자세한 내용은 참조 [하는 방법: Visual Studio에서 Office 만들기 프로젝트](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.  
  
     Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **내 Excel 작업 창의** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="add-a-new-data-source-to-the-project"></a>새 데이터 원본을 프로젝트에 추가  
  
### <a name="to-add-a-new-data-source-to-the-project"></a>프로젝트에 새 데이터 원본을 추가 하려면  
  
1.  경우는 **데이터 원본** 창이 표시 되지 않으면 메뉴 모음에서 선택에 의해 표시, **보기** > **다른 창**  >   **데이터 원본**합니다.  
  
2.  **새 데이터 소스 추가** 를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  선택 **데이터베이스** 클릭 하 고 **다음**합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 데이터 연결을 선택 하거나 새 연결을 사용 하 여 추가 된 **새 연결** 단추입니다.  
  
5.  **다음**을 클릭합니다.  
  
6.  옵션을 선택 하는 경우 연결을 저장 하 고 클릭 한 다음의 선택을 취소 **다음**합니다.  
  
7.  확장 된 **테이블** 에서 노드는 **데이터베이스 개체** 창.  
  
8.  옆에 확인란을 선택 된 **Suppliers** 테이블입니다.  
  
9. 확장 된 **제품** 테이블을 선택한 **ProductName**, **SupplierID**, **QuantityPerUnit**, 및 **UnitPrice**.  
  
10. **마침**을 클릭합니다.  
  
 마법사에서 추가 **Suppliers** 테이블 및 **제품** 테이블는 **데이터 소스** 창. 또한 형식화 된 데이터 집합에 표시 되는 프로젝트에 추가 **솔루션 탐색기**합니다.  
  
## <a name="add-controls-to-the-worksheet"></a>워크시트에 컨트롤 추가  
 다음에 추가 <xref:Microsoft.Office.Tools.Excel.NamedRange> 제어 및 <xref:Microsoft.Office.Tools.Excel.ListObject> 첫 번째 워크시트를 제어 합니다.  
  
### <a name="to-add-a-namedrange-control-and-a-listobject-control"></a>NamedRange 컨트롤 및 ListObject 컨트롤을 추가 하려면  
  
1.  되어 있는지 확인는 **내 Excel 작업 Pane.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 `Sheet1` 표시 합니다.  
  
2.  에 **데이터 원본** 창 확장는 **Suppliers** 테이블입니다.  
  
3.  드롭다운 화살표를 클릭는 **회사 이름** 노드를 차례로 클릭 한 다음 **NamedRange**합니다.  
  
4.  끌기 **회사 이름** 에서 **데이터 원본** 셀에는 창 **A2** 에서 `Sheet1`합니다.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 컨트롤 `CompanyNameNamedRange` 만들어지면 및 텍스트 \<CompanyName > 셀에 표시 **A2**합니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `suppliersBindingSource`, 테이블 어댑터 및 <xref:System.Data.DataSet> 프로젝트에 추가 합니다. 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingSource>에 바인딩된 차례로 <xref:System.Data.DataSet> 인스턴스.  
  
5.  에 **데이터 원본** 창 아래에 있는 열을 지 나 아래로 스크롤하여는 **Suppliers** 테이블입니다. 목록의 맨 아래에는 **제품** ; 테이블의 자식 이기 때문에 여기는 **Suppliers** 테이블입니다. 이 옵션을 선택 **제품** 테이블을 동일한 수준으로 중이 아닌는 **Suppliers** 테이블을 선택한 다음 표시 되는 드롭다운 화살표를 클릭 합니다.  
  
6.  클릭 **ListObject** 다음 끌어서 드롭 다운 목록에는 **제품** 테이블 셀으로 **A6** 에 `Sheet1`합니다.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> 라는 컨트롤 `ProductNameListObject` 셀에 작성 **A6**합니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `productsBindingSource` 테이블 어댑터 프로젝트에 추가 됩니다. 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingSource>에 바인딩된 차례로 <xref:System.Data.DataSet> 인스턴스.  
  
7.  C#에 해당, 선택 **suppliersBindingSource** 변경 되며 구성 요소 트레이 **한정자** 속성을 **내부** 에 **속성** 창.  
  
## <a name="add-controls-to-the-actions-pane"></a>작업 창에 컨트롤 추가  
 다음으로, 콤보 상자에 있는 작업 창 컨트롤을 해야 합니다.  
  
### <a name="to-add-an-actions-pane-control"></a>작업 창 컨트롤을 추가 하려면  
  
1.  선택 된 **내 Excel 작업 창의** 프로젝트에서 **솔루션 탐색기**합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**, 이름을 **actionscontrol로 지정한**를 클릭 하 고 **추가**합니다.  
  
### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤을 추가 하려면  
  
1.  **공용 컨트롤** 의 탭은 **도구 상자**, 끌어는 <xref:System.Windows.Forms.ComboBox> 작업 창 컨트롤을 제어 합니다.  
  
2.  변경 된 **크기** 속성을 **171, 21**합니다.  
  
3.  콤보 상자에 맞게 사용자 정의 컨트롤의 크기를 조정 합니다.  
  
## <a name="bind-the-control-on-the-actions-pane-to-data"></a>데이터에 작업 창에 컨트롤 바인딩  
 이 섹션에서는 데이터 원본 설정에서 <xref:System.Windows.Forms.ComboBox> 로 동일한 데이터 원본에는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 워크시트에 컨트롤.  
  
### <a name="to-set-data-binding-properties-of-the-control"></a>컨트롤의 데이터 바인딩 속성을 설정 하려면  
  
1.  작업 창 컨트롤을 마우스 오른쪽 단추로 누른 **코드 보기**합니다.  
  
2.  다음 코드를 추가 하는 <xref:System.Windows.Forms.UserControl.Load> 작업 창 컨트롤의 이벤트입니다.  
  
     [!code-vb[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#1)]  
  
3.  C#에서 이벤트 처리기를 만들어야 합니다는 `ActionsControl`합니다. 이 코드를 배치할 수 있습니다는 `ActionsControl` 생성자입니다. 이벤트 처리기를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#2)]  
  
## <a name="show-the-actions-pane"></a>작업 창 표시  
 작업 창에서 런타임에 컨트롤을 추가할 때까지 표시 되지 않습니다.  
  
#### <a name="to-show-the-actions-pane"></a>작업 창을 표시 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 *ThisWorkbook.vb* 또는 *ThisWorkbook.cs*, 클릭 하 고 **코드 보기**합니다.  
  
2.  사용자 정의 컨트롤의 새 인스턴스를 만들고는 `ThisWorkbook` 클래스입니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#3)]  
  
3.  에 <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> 의 이벤트 처리기 `ThisWorkbook`, 작업 창에 컨트롤을 추가 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#4)]  
  
## <a name="test-the-application"></a>응용 프로그램 테스트  
 이제 문서를 열 때 작업 창이 열리고 있는지 및 컨트롤은 마스터/세부 관계를가지고 있는지 확인 하 여 문서를 테스트할 수 있습니다.  
  
### <a name="to-test-your-document"></a>문서를 테스트하려면  
  
1.  키를 눌러 **F5** 프로젝트를 실행 합니다.  
  
2.  작업 창이 표시 되는지 확인 합니다.  
  
3.  목록 상자에 회사를 선택 합니다. 회사 이름에 나열 되어 있는지 확인 하십시오.는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 제어 되며 제품 세부 정보에 나열 됩니다는 <xref:Microsoft.Office.Tools.Excel.ListObject> 제어 합니다.  
  
4.  회사 이름을 확인 하는 다양 한 회사를 선택 하 고 제품 세부 정보를 적절 하 게 변경 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   Word에서 컨트롤에 데이터 바인딩 자세한 내용은 참조 [연습: Word 작업 창의 컨트롤에 데이터를 바인딩할](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)합니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  