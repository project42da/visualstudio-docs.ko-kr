---
title: "연습: Windows Forms 간에 데이터 전달 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 폼 간 전달"
  - "폼, 데이터 전달"
  - "연습[Visual Studio], 데이터"
  - "연습[Windows Forms], 데이터"
  - "Windows Forms, 연습"
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: Windows Forms 간에 데이터 전달
이 연습에서는 폼 간에 데이터를 전달하기 위한 단계별 지침을 제공합니다.  Northwind 폼의 Customers 및 Orders 테이블을 사용하는 경우 한 폼에서 고객을 선택하면 선택한 고객의 주문이 두 번째 폼에 표시됩니다.  이 연습에서는 첫 번째 폼의 데이터를 받는 폼에서 메서드를 만드는 방법을 보여줍니다.  
  
> [!NOTE]
>  이 연습에서는 폼 간에 데이터를 전달하는 방식 중 하나만을 보여줍니다.  폼에 데이터를 전달하는 다른 옵션도 있습니다. 예를 들어 데이터를 받는 두 번째 생성자를 만들거나 첫 번째 폼의 데이터를 사용하여 설정 가능한 공용 속성을 만드는 방식을 사용할 수도 있습니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 데이터 집합을 만들고 구성합니다.  
  
-   **데이터 소스** 창에서 항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
-   **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
-   데이터를 표시하는 표가 포함된 두 번째 폼을 만듭니다.  
  
-   특정 고객의 주문을 가져오는 TableAdapter 쿼리를 만듭니다.  
  
-   폼 간에 데이터를 전달합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Windows 응용 프로그램 만들기  
  
#### 새 Windows 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `PassingDataBetweenForms`로 지정합니다.  
  
3.  **Windows Forms 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **PassingDataBetweenForms** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터 소스 만들기  
  
#### 데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터베이스 모델 선택** 페이지에서 **데이터 집합**이 지정되어 있는지 확인하고 **다음**을 클릭합니다.  
  
5.  **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 선택하여 **연결 추가\/수정** 대화 상자를 시작합니다.  
  
6.  데이터베이스에 암호가 필요하며 중요한 데이터를 포함하도록 옵션이 설정되어 있으면 해당 옵션을 선택하고 **다음**을 클릭합니다.  
  
7.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
8.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
9. **Customers** 및 **Orders** 테이블을 선택한 다음 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 **Customers** 및 Orders 테이블이 **데이터 소스** 창에 나타납니다.  
  
## 첫 번째 폼\(Form1\) 만들기  
 **데이터 소스** 창에서 폼으로 **Customers** 노드를 끌어 데이터 바인딩된 표\(<xref:System.Windows.Forms.DataGridView>\)를 만들 수 있습니다.  
  
#### 폼에서 데이터 바인딩된 표를 만들려면  
  
-   주 **Customers** 노드를 **데이터 소스** 창에서 **Form1**로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 **Form1**에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
## 두 번째 폼\(Form2\) 만들기  
  
#### 데이터를 전달할 두 번째 폼을 만들려면  
  
1.  **프로젝트** 메뉴에서 **Windows Form 추가**를 선택합니다.  
  
2.  기본 이름인 **Form2**를 그대로 두고 **추가**를 클릭합니다.  
  
3.  주 **Orders** 노드를 **데이터 소스** 창에서 **Form2**로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 **Form2**에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
4.  구성 요소 트레이에서 **OrdersBindingNavigator**를 삭제합니다.  
  
     **OrdersBindingNavigator**가 **Form2**에서 사라집니다.  
  
## Form1에서 선택한 고객의 주문을 로드하도록 Form2에 TableAdapter 쿼리 추가  
  
#### TableAdapter 쿼리를 만들려면  
  
1.  **솔루션 탐색기**에서 **NorthwindDataSet.xsd** 파일을 두 번 클릭합니다.  
  
2.  **OrdersTableAdapter**를 마우스 오른쪽 단추로 클릭하고 **쿼리 추가**를 선택합니다.  
  
3.  기본 옵션인 **SQL 문 사용**을 그대로 두고 **다음**을 클릭합니다.  
  
4.  기본 옵션인 **행을 반환하는 SELECT**를 그대로 두고 **다음**을 클릭합니다.  
  
5.  `CustomerID`를 기준으로 `Orders`를 반환하는 WHERE 절을 쿼리에 추가합니다.  이 쿼리는 다음과 같아야 합니다.  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  데이터베이스에 대한 올바른 매개 변수 구문을 확인합니다.  예를 들어 Microsoft Access에서 WHERE 절은 다음과 같습니다. `WHERE CustomerID = ?`.  
  
6.  **다음**을 클릭합니다.  
  
7.  **DataTable 채우기 메서드 이름**에는 `FillByCustomerID`를 입력합니다.  
  
8.  **DataTable 반환** 옵션 선택을 취소하고 **다음**을 클릭합니다.  
  
9. **마침**을 클릭합니다.  
  
## Form2에 데이터를 전달할 메서드 만들기  
  
#### 데이터를 전달할 메서드를 만들려면  
  
1.  **Form2**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택하여 **코드 편집기**에서 **Form2**를 엽니다.  
  
2.  다음 코드를 **Form2**의 `Form2_Load` 메서드 뒤에 추가합니다.  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-cs[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## Form1에서 데이터를 전달하고 Form2를 표시하는 메서드 만들기  
  
#### Form2로 데이터를 전달할 메서드를 만들려면  
  
1.  **Form1**에서 Customer 데이터 표를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
2.  **속성** 창에서 **Events**를 클릭합니다.  
  
3.  **CellDoubleClick** 이벤트를 두 번 클릭합니다.  
  
     코드 편집기가 나타납니다.  
  
4.  다음 샘플과 일치하도록 메서드 정의를 업데이트합니다.  
  
     [!code-cs[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## 응용 프로그램 실행  
  
#### 응용 프로그램을 실행하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
-   **Form1**에서 고객 레코드를 두 번 클릭하여 해당 고객의 주문이 포함된 **Form2**를 엽니다.  
  
## 다음 단계  
 응용 프로그램 요구 사항에 따라 폼 간에 데이터를 전달한 후 몇 단계를 더 수행해야 할 수도 있습니다.  이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   데이터 집합을 편집하여 데이터베이스 개체를 추가하거나 편집합니다.  자세한 내용은 [방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)을 참조하십시오.  
  
-   데이터를 데이터베이스로 다시 보내는 기능을 추가합니다.  자세한 내용은 [방법: 데이터베이스에 데이터 집합 변경 내용 저장](../Topic/How%20to:%20Save%20Dataset%20Changes%20to%20a%20Database.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)