---
title: "연습: Word 작업 창의 컨트롤에 데이터 바인딩"
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
  - "작업 창[Visual Studio에서 Office 개발], 컨트롤 바인딩"
  - "작업 창[Visual Studio에서 Office 개발], 데이터 바인딩"
  - "컨트롤[Visual Studio에서 Office 개발], 데이터 바인딩"
  - "데이터 바인딩[Visual Studio에서 Office 개발], 작업 창"
  - "데이터 바인딩[Visual Studio에서 Office 개발], 스마트 문서"
  - "스마트 문서[Visual Studio에서 Office 개발], 데이터 바인딩"
ms.assetid: 5ef72fc7-412b-4454-9890-4479a13ee7f9
caps.latest.revision: 64
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 63
---
# 연습: Word 작업 창의 컨트롤에 데이터 바인딩
  이 연습에서는 Word에서 작업 창의 컨트롤에 데이터 바인딩을 보여 줍니다.  컨트롤은 SQL Server 데이터베이스에 있는 테이블 간의 마스터\/세부 관계를 나타냅니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   데이터에 바인딩되는 Windows Forms 컨트롤이 포함된 작업 창 만들기  
  
-   마스터\/세부 관계를 사용하여 컨트롤에 데이터 표시  
  
-   응용 프로그램을 열 때 작업 창 표시  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
-   SQL Server 데이터베이스에서 읽고 쓰기 위한 권한이 있어야 합니다.  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  이름이 My Word Actions Pane인 Word 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Word 문서가 열리고 **My Word Actions Pane** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 작업 창에 컨트롤 추가  
 이 연습에서는 데이터 바인딩된 Windows Forms 컨트롤이 포함된 작업 창 컨트롤이 필요합니다.  데이터 소스를 프로젝트에 추가한 다음 **데이터 소스** 창에서 작업 창 컨트롤로 컨트롤을 끌어 놓습니다.  
  
#### 작업 창 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **My Word Actions Pane** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**을 선택하고 이름을 **ActionsControl**로 지정한 다음 **추가**를 클릭합니다.  
  
#### 프로젝트에 데이터 소스를 추가하려면  
  
1.  경우는  **데이터 원본** 창이 표시 되지 않는,이, 메뉴 표시줄에서 선택 표시  **보기**,  **기타 Windows**,  **데이터 원본**.  
  
    > [!NOTE]  
    >  **데이터 소스 표시**를 사용할 수 없으면 Word 문서를 클릭한 다음 다시 확인합니다.  
  
2.  **새 데이터 소스 추가**를 클릭하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 대한 데이터 연결을 선택하거나 **새 연결** 단추를 사용하여 새 연결을 추가합니다.  
  
5.  **다음**을 클릭합니다.  
  
6.  연결을 저장하는 옵션이 선택되어 있는 경우 선택을 취소하고 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체** 창에서 **테이블** 노드를 확장합니다.  
  
8.  **Suppliers** 및 **Products** 테이블 옆에 있는 확인란을 선택합니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에서 **Suppliers** 테이블과 **Products** 테이블이 **데이터 소스** 창에 추가됩니다.  **솔루션 탐색기**에 표시되는 프로젝트에 형식화된 데이터 집합도 추가됩니다.  
  
#### 작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤을 추가하려면  
  
1.  **데이터 소스** 창에서 **Suppliers** 테이블을 확장합니다.  
  
2.  **Company Name** 노드에서 드롭다운 화살표를 클릭하고 **ComboBox**를 선택합니다.  
  
3.  **CompanyName**을 **데이터 소스** 창에서 작업 창 컨트롤에 끌어 놓습니다.  
  
     작업 창 컨트롤에 <xref:System.Windows.Forms.ComboBox> 컨트롤이 작성됩니다.  이와 함께 `SuppliersBindingSource`라는 <xref:System.Windows.Forms.BindingSource>, 테이블 어댑터 및 <xref:System.Data.DataSet>이 구성 요소 트레이에서 프로젝트에 추가됩니다.  
  
4.  **구성 요소** 트레이에서 `SuppliersBindingNavigator`를 선택하고 Delete 키를 누릅니다.  이 연습에서는 `SuppliersBindingNavigator`를 사용하지 않습니다.  
  
    > [!NOTE]  
    >  `SuppliersBindingNavigator`를 삭제해도 이와 관련하여 생성된 모든 코드는 제거되지 않습니다.  이 코드를 직접 제거할 수 있습니다.  
  
5.  콤보 상자를 레이블 아래로 옮기고 **Size** 속성을 171, 21로 변경합니다.  
  
6.  **데이터 소스** 창에서 **Suppliers** 표의 자식인 **Products** 표를 확장합니다.  
  
7.  **ProductName** 노드에서 드롭다운 화살표를 클릭하고 **ListBox**를 선택합니다.  
  
8.  **ProductName**을 작업 창 컨트롤에 끌어 놓습니다.  
  
     작업 창 컨트롤에 <xref:System.Windows.Forms.ListBox> 컨트롤이 작성됩니다.  이와 함께 `ProductBindingSource`라는 <xref:System.Windows.Forms.BindingSource>와 테이블 어댑터가 구성 요소 트레이에서 프로젝트에 추가됩니다.  
  
9. 목록 상자를 레이블 아래로 옮기고 **Size** 속성을 171,95로 변경합니다.  
  
10. <xref:System.Windows.Forms.Button>을 **도구 상자**에서 작업 창 컨트롤로 끌어 목록 상자 아래에 배치합니다.  
  
11. <xref:System.Windows.Forms.Button>을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 클릭한 후 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**Insert**|  
    |**텍스트**|**Insert**|  
  
12. 컨트롤에 맞도록 사용자 정의 컨트롤의 크기를 조정합니다.  
  
## 데이터 소스 설정  
 데이터 소스를 설정하려면 작업 창 컨트롤의 <xref:System.Windows.Forms.UserControl.Load> 이벤트에 컨트롤을 <xref:System.Data.DataTable>의 데이터로 채우는 코드를 추가하고 각 컨트롤의 <xref:System.Windows.Forms.Binding.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성을 설정합니다.  
  
#### 데이터와 함께 컨트롤을 로드하려면  
  
1.  `ActionsControl` 클래스의 <xref:System.Windows.Forms.UserControl.Load> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#1)]
     [!code-vb[Trin_VstcoreActionsPaneWord#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ActionsControl.vb#1)]  
  
2.  C\#에서는 <xref:System.Windows.Forms.UserControl.Load> 이벤트에 이벤트 처리기를 연결해야 합니다.  이 코드를 `ActionsControl` 생성자에서 `InitializeComponent`에 대한 호출 밑에 배치할 수 있습니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#33](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#33)]  
  
#### 컨트롤의 데이터 바인딩 속성을 설정하려면  
  
1.  `CompanyNameComboBox` 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 **DataSource** 속성의 오른쪽에 있는 단추를 클릭하고 **suppliersBindingSource**를 선택합니다.  
  
3.  **DisplayMember** 속성의 오른쪽에 있는 단추를 클릭하고 **CompanyName**을 선택합니다.  
  
4.  **DataBindings** 속성을 확장하고 **Text** 속성의 오른쪽에 있는 단추를 클릭한 다음 **없음**을 선택합니다.  
  
5.  `ProductNameListBox` 컨트롤을 선택합니다.  
  
6.  **속성** 창에서 **DataSource** 속성의 오른쪽에 있는 단추를 클릭하고 **productsBindingSource**를 선택합니다.  
  
7.  **DisplayMember** 속성의 오른쪽에 있는 단추를 클릭하고 **ProductName**을 선택합니다.  
  
8.  **DataBindings** 속성을 확장하고 **SelectedValue** 속성의 오른쪽에 있는 단추를 클릭한 다음 **없음**을 선택합니다.  
  
## 표에 데이터를 삽입하기 위한 메서드 추가  
 다음 작업에서는 바인딩된 컨트롤의 데이터를 읽어 Word 문서의 표를 채웁니다.  먼저 표의 머리글 서식을 지정하는 프로시저를 만든 다음 `AddData` 메서드를 추가하여 Word 표를 만들고 서식을 지정합니다.  
  
#### 표 머리글을 서식 지정하려면  
  
1.  `ActionsControl` 클래스에서 표의 머리글을 서식 지정하는 메서드를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#2)]
     [!code-vb[Trin_VstcoreActionsPaneWord#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ActionsControl.vb#2)]  
  
#### 표를 만들려면  
  
1.  `ActionsControl` 클래스에서 표가 하나도 없는 경우 표를 만드는 메서드를 작성하고 작업 창의 데이터를 표에 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneWord#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ActionsControl.vb#3)]  
  
#### Word 표에 텍스트를 삽입하려면  
  
1.  **삽입** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneWord#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ActionsControl.vb#4)]  
  
2.  C\#의 경우 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.  `ActionsControl` 클래스의 <xref:System.Windows.Forms.UserControl.Load> 이벤트 처리기에 이 코드를 넣을 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ActionsControl.cs#5)]  
  
## 작업 창 표시  
 작업 창은 컨트롤을 추가한 후에 표시됩니다.  
  
#### 작업 창을 표시하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 **ThisDocument.vb** 또는 **ThisDocument.cs**를 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  다음 예제와 같이 `ThisDocument` 클래스의 맨 위에 컨트롤의 새 인스턴스를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#6)]
     [!code-vb[Trin_VstcoreActionsPaneWord#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#6)]  
  
3.  다음 예제와 같이 `ThisDocument`의 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트 처리기에 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreActionsPaneWord#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#7)]  
  
## 응용 프로그램 테스트  
 이제 문서를 테스트하여 문서를 열 때 작업 창이 함께 나타나는지 확인할 수 있습니다.  작업 창의 컨트롤에서 마스터\/세부 관계를 테스트하고 **삽입** 단추를 클릭할 때 Word 표에 데이터가 채워지는지 확인합니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  작업 창이 표시되는지 확인합니다.  
  
3.  콤보 상자에서 회사를 선택하고 **Products** 목록 상자의 항목이 변경되는지 확인합니다.  
  
4.  제품을 선택하고 작업 창에서 **삽입**을 클릭하여 제품 세부 사항이 Word의 표에 추가되는지 확인합니다.  
  
5.  여러 회사의 다른 제품을 삽입합니다.  
  
## 다음 단계  
 이 연습에서는 Word의 작업 창에 있는 컨트롤에 데이터를 바인딩하는 기본적인 방법을 보여 줍니다.  다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   Excel의 컨트롤에 데이터를 바인딩합니다.  자세한 내용은 [연습: Excel 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)을 참조하십시오.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)을 참조하십시오.  
  
## 참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  