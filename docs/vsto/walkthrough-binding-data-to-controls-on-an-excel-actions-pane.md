---
title: "연습: Excel 작업 창의 컨트롤에 데이터 바인딩"
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
ms.assetid: 106c07bd-e931-4dc5-94dc-ca43900fe09d
caps.latest.revision: 63
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 62
---
# 연습: Excel 작업 창의 컨트롤에 데이터 바인딩
  이 연습에서는 Microsoft Office Excel의 작업 창에 있는 컨트롤에 데이터를 바인딩하는 방법을 보여 줍니다.  컨트롤은 SQL Server 데이터베이스에 있는 테이블 간의 마스터\/세부 관계를 나타냅니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   워크시트에 컨트롤 추가  
  
-   작업 창 컨트롤 만들기  
  
-   작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤 추가  
  
-   응용 프로그램을 열 때 작업 창 표시  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
-   SQL Server 데이터베이스에서 읽고 쓰기 위한 권한이 있어야 합니다.  
  
## 프로젝트 만들기  
 첫 번째 단계는 Excel 통합 문서 프로젝트 만들기입니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  My Excel Actions Pane이라는 Excel 통합 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 **My Excel Actions Pane** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 프로젝트에 새 데이터 소스 추가  
  
#### 프로젝트에 새 데이터 소스를 추가하려면  
  
1.  경우는  **데이터 원본** 창이 표시 되지 않는,이, 메뉴 표시줄에서 선택 표시  **보기**,  **기타 Windows**,  **데이터 원본**.  
  
2.  선택  **새 데이터 소스 추가** 시작 하는  **데이터 소스 구성 마법사**.  
  
3.  **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 대한 데이터 연결을 선택하거나 **새 연결** 단추를 사용하여 새 연결을 추가합니다.  
  
5.  **다음**을 클릭합니다.  
  
6.  연결을 저장하는 옵션이 선택되어 있는 경우 선택을 취소하고 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체** 창에서 **테이블** 노드를 확장합니다.  
  
8.  **Suppliers** 테이블 옆에 있는 확인란을 선택합니다.  
  
9. **Products** 테이블을 확장하고 **ProductName**, **SupplierID**, **QuantityPerUnit** 및 **UnitPrice**를 선택합니다.  
  
10. **마침**을 클릭합니다.  
  
 마법사에서 **Suppliers** 테이블과 **Products** 테이블이 **데이터 소스** 창에 추가됩니다.  **솔루션 탐색기**에 표시되는 프로젝트에 형식화된 데이터 집합도 추가됩니다.  
  
## 워크시트에 컨트롤 추가  
 이제 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤과 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 첫 번째 워크시트에 추가합니다.  
  
#### NamedRange 컨트롤 및 ListObject 컨트롤을 추가하려면  
  
1.  확인은  **내 Excel 작업 Pane.xlsx** 통합 문서가 Visual Studio 디자이너에 열려 있는와 `Sheet1` 표시 합니다.  
  
2.  **데이터 소스** 창에서 **Suppliers** 테이블을 확장합니다.  
  
3.  **Company Name** 노드에서 드롭다운 화살표를 클릭하고 **NamedRange**를 선택합니다.  
  
4.  **데이터 소스** 창에서 **Company Name**을 끌어 `Sheet1`의 **A2**에 놓습니다.  
  
     `CompanyNameNamedRange`라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 작성되고 \<CompanyName\> 텍스트가 셀 **A2**에 나타납니다.  이와 함께 `suppliersBindingSource`라는 <xref:System.Windows.Forms.BindingSource>, 테이블 어댑터 및 <xref:System.Data.DataSet>이 프로젝트에 추가됩니다.  컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 <xref:System.Data.DataSet> 인스턴스에 바인딩됩니다.  
  
5.  **데이터 소스** 창에서 **Suppliers** 테이블 아래의 열 밑으로 스크롤합니다.  목록 아래쪽에 **Products** 테이블이 있습니다. 이 테이블은 **Suppliers** 테이블의 자식이기 때문에 이와 같은 위치에 있습니다.  **Suppliers** 테이블과 동일한 수준에 있는 테이블이 아닌 이 **Products** 테이블을 선택한 다음 드롭다운 화살표를 클릭합니다.  
  
6.  드롭다운 목록에서 **ListObject**를 클릭하고 **Products** 테이블을 `Sheet1`의 셀 **A6**에 끌어 놓습니다.  
  
     `ProductNameListObject`라는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 셀 **A6**에 작성됩니다.  이와 함께 `productsBindingSource`라는 <xref:System.Windows.Forms.BindingSource>와 테이블 어댑터가 프로젝트에 추가됩니다.  컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 <xref:System.Data.DataSet> 인스턴스에 바인딩됩니다.  
  
7.  C\#의 경우, 구성 요소 트레이에서 **suppliersBindingSource**를 선택하고 **속성** 창에서 **Modifiers** 속성을 Internal로 변경합니다.  
  
## 작업 창에 컨트롤 추가  
 이제 콤보 상자가 포함된 작업 창 컨트롤이 필요합니다.  
  
#### 작업 창 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **My Excel Actions Pane** 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **작업 창 컨트롤**을 선택하고 이름을 **ActionsControl**로 지정한 다음 **추가**를 클릭합니다.  
  
#### 작업 창 컨트롤에 데이터 바인딩된 Windows Forms 컨트롤을 추가하려면  
  
1.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:System.Windows.Forms.ComboBox> 컨트롤을 작업 창 컨트롤에 끌어 놓습니다.  
  
2.  **Size** 속성을 171, 21로 변경합니다.  
  
3.  콤보 상자에 맞도록 사용자 정의 컨트롤의 크기를 조정합니다.  
  
## 작업 창의 컨트롤을 데이터에 바인딩  
 이 단원에서는 <xref:System.Windows.Forms.ComboBox>의 데이터 소스를 워크시트의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤과 동일한 데이터 소스로 설정합니다.  
  
#### 컨트롤의 데이터 바인딩 속성을 설정하려면  
  
1.  작업 창 컨트롤을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
2.  작업 창 컨트롤의 <xref:System.Windows.Forms.UserControl.Load> 이벤트에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ActionsControl.cs#1)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ActionsControl.vb#1)]  
  
3.  C\#의 경우 `ActionsControl`에 대한 이벤트 처리기를 만들어야 합니다.  이 코드를 `ActionsControl` 생성자에 배치할 수 있습니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ActionsControl.cs#2)]  
  
## 작업 창 표시  
 작업 창은 런타임에 컨트롤을 추가할 때까지 표시되지 않습니다.  
  
#### 작업 창을 표시하려면  
  
1.  **솔루션 탐색기**에서 ThisWorkbook.vb 또는 ThisWorkbook.cs를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
2.  `ThisWorkbook` 클래스에 사용자 정의 컨트롤의 새 인스턴스를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ThisWorkbook.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ThisWorkbook.vb#3)]  
  
3.  `ThisWorkbook`의 <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> 이벤트 처리기에서 작업 창에 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ThisWorkbook.vb#4)]  
  
## 응용 프로그램 테스트  
 이제 문서를 테스트하여 문서를 열 때 작업 창이 열리고 컨트롤에 마스터\/세부 항목 관계가 있는지 확인할 수 있습니다.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  작업 창이 표시되는지 확인합니다.  
  
3.  목록 상자에서 회사를 선택합니다.  회사 이름이 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤에 나열되고 제품 세부 사항이 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에 나열되는지 확인합니다.  
  
4.  여러 회사를 선택하여 회사 이름과 제품 세부 사항이 올바르게 변경되는지 확인합니다.  
  
## 다음 단계  
 다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   Word의 컨트롤에 데이터를 바인딩합니다.  자세한 내용은 [연습: Word 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)을 참조하십시오.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)을 참조하십시오.  
  
## 참고 항목  
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  