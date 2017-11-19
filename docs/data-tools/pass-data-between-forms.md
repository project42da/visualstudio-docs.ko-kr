---
title: "폼 간에 데이터를 전달 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f401224657e64922fc9f6102a33eaf1cf824a556
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="pass-data-between-forms"></a>폼 간에 데이터를 전달 합니다.
이 연습에서는 폼 간에 데이터를 전달하기 위한 단계별 지침을 제공합니다. customers 및 orders 테이블에서 Northwind 사용 하 여 한 가지 형태 고객을 선택할 수 있습니다 및 두 번째 형태에 선택한 고객의 주문이 표시 됩니다. 이 연습에서는 첫 번째 형태에서 데이터를 받는 두 번째 형태에서 메서드를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 연습에서는 폼 간에 데이터를 전달하는 방식 중 하나만을 보여줍니다. 데이터를 받는 두 번째 생성자를 만드는 등 폼에 데이터를 전달 하기 위한 다른 옵션은 하거나는 공용 속성을 만들 설정 데이터로 첫 번째 형태에서 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows Forms 응용 프로그램** 프로젝트.  
  
-   만들기 및 구성 된 데이터 집합의 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)합니다.  
  
-   항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택 하 고 **데이터 소스** 창. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
-   항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다는 **데이터 소스** 창에서 폼으로 합니다.  
  
-   데이터를 표시하는 표가 포함된 두 번째 폼을 만듭니다.  
  
-   특정 고객의 주문을 가져오는 TableAdapter 쿼리를 만듭니다.  
  
-   폼 간에 데이터를 전달합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server 버전의 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
## <a name="create-the-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **PassingDataBetweenForms**를 선택한 후 **확인**합니다. 
  
     **PassingDataBetweenForms** 프로젝트 생성 되며에 추가할 **솔루션 탐색기**합니다.  
  
## <a name="create-the-data-source"></a>데이터 원본 만들기  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성** 마법사.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.  
  
4.  에 **데이터베이스 모델 선택** 페이지에서 **Dataset** 를 지정 하 고 클릭 **다음**합니다.  
  
5.  에 **데이터 연결 선택** 페이지에서 다음 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.  
  
6.  데이터베이스에 암호가 필요 하 고 중요 한 데이터를 포함 하려면이 옵션은 사용할 옵션을 선택 하 고 클릭 **다음**합니다.  
  
7.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지 **다음**합니다.  
  
8.  에 **데이터베이스 개체 선택** 페이지는 **테이블** 노드.  
  
9. 선택 된 **고객** 및 **Orders** 테이블과 클릭 한 다음 **마침**합니다.  
  
     **NorthwindDataSet** 프로젝트에 추가 및 **고객** 및 **Orders** 에 테이블이 나타나는 **데이터 소스** 창.  
  
## <a name="create-the-first-form-form1"></a>첫 번째 폼 (Form1) 만들기  
 데이터 바인딩된 표를 만들 수 있습니다 (한 <xref:System.Windows.Forms.DataGridView> 제어)를 끌어는 **고객** 에서 노드는 **데이터 원본** 창에서 폼으로 합니다.  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>폼에서 데이터 바인딩된 표를 만들려면  
  
-   주 끌어 **고객** 에서 노드는 **데이터 원본** 창으로 **Form1**합니다.  
  
     A <xref:System.Windows.Forms.DataGridView> 및 도구 스트립 (<xref:System.Windows.Forms.BindingNavigator>)에 표시할 레코드 탐색을 위한 **Form1**합니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
## <a name="create-the-second-form-form2"></a>두 번째 폼 (Form2) 만들기  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>데이터를 전달할 두 번째 폼을 만들려면  
  
1.  **프로젝트** 메뉴에서 **Windows Form 추가**를 선택합니다.  
  
2.  기본 이름을 그대로 **Form2**를 클릭 하 고 **추가**합니다.  
  
3.  주 끌어 **Orders** 에서 노드는 **데이터 원본** 창으로 **Form2**합니다.  
  
     A <xref:System.Windows.Forms.DataGridView> 및 도구 스트립 (<xref:System.Windows.Forms.BindingNavigator>)에 표시할 레코드 탐색을 위한 **Form2**합니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
4.  삭제 된 **OrdersBindingNavigator** 요소 트레이에서 합니다.  
  
     **OrdersBindingNavigator** 에서 사라집니다 **Form2**합니다.  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>Form1에서 선택한 고객의 주문을 로드 하도록 Form2 TableAdapter 쿼리 추가  
  
#### <a name="to-create-a-tableadapter-query"></a>TableAdapter 쿼리를 만들려면  
  
1.  두 번 클릭 하 여 **NorthwindDataSet.xsd** 파일을 **솔루션 탐색기**합니다.  
  
2.  마우스 오른쪽 단추로 클릭는 **OrdersTableAdapter**를 선택 하 고 **쿼리 추가**합니다.  
  
3.  기본 옵션인 **SQL 문 사용**, 클릭 하 고 **다음**합니다.  
  
4.  기본 옵션인 **행을 반환 하는 SELECT**, 클릭 하 고 **다음**합니다.  
  
5.  반환할 쿼리에 WHERE 절을 추가 `Orders` 기반는 `CustomerID`합니다. 이 쿼리는 다음과 같아야 합니다.  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  데이터베이스에 대한 올바른 매개 변수 구문을 확인합니다. 예를 들어 Microsoft Access에서 WHERE 절은 다음과 같습니다. `WHERE CustomerID = ?`.  
  
6.  **다음**을 클릭합니다.  
  
7.  에 대 한는 **DataTableMethod 이름은 채우기**, 형식 `FillByCustomerID`합니다.  
  
8.  지우기는 **DataTable 반환** 옵션을 선택한 다음 클릭 **다음**합니다.  
  
9. **마침**을 클릭합니다.  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>데이터를 전달 하는 Form2에는 메서드를 만듭니다.  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>데이터를 전달할 메서드를 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **Form2**를 선택 하 고 **코드 보기** 열려는 **Form2** 에 **코드 편집기**합니다.  
  
2.  다음 코드를 추가 **Form2** 후의 `Form2_Load` 메서드:  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-csharp[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>데이터 전달 하 고 Form2 표시할 Form1 메서드 만들기  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Form2로 데이터를 전달할 메서드를 만들려면  
  
1.  **Form1**Customer 데이터 표를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
2.  에 **속성** 창 클릭 **이벤트**합니다.  
  
3.  두 번 클릭 하 여 **CellDoubleClick** 이벤트입니다.  
  
     코드 편집기가 나타납니다.  
  
4.  다음 샘플과 일치하도록 메서드 정의를 업데이트합니다.  
  
     [!code-csharp[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## <a name="run-the-application"></a>응용 프로그램 실행  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
-   고객 레코드를 두 번 클릭 **Form1** 열려는 **Form2** 해당 고객의 주문 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 폼 간에 데이터를 전달한 후 몇 단계를 더 수행해야 할 수도 있습니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   데이터 집합을 편집하여 데이터베이스 개체를 추가하거나 편집합니다. 자세한 내용은 [데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)을 참조하세요.  
  
-   데이터를 데이터베이스로 다시 보내는 기능을 추가합니다. 자세한 내용은 참조 [데이터는 데이터베이스에 다시 저장](../data-tools/save-data-back-to-the-database.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)