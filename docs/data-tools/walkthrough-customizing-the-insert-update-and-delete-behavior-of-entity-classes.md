---
title: "연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 03ff1146-706e-4780-91cb-56a83df63eea
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c5be469cd93ce0b920e9100b43d642fd96427a79
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2018
---
# <a name="walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes"></a>연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제

[LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 만들고 편집 하기 위한 시각적 디자인 화면을 제공 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 데이터베이스의 개체를 기반으로 하는 클래스 (엔터티 클래스). 사용 하 여 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index), SQL 데이터베이스에 액세스 하려면 LINQ 기술에 사용할 수 있습니다. 자세한 내용은 [LINQ(Language-Integrated Query)](/dotnet/csharp/linq/)를 참조하세요.  
  
기본적으로 업데이트를 수행하는 논리는 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임에서 제공합니다. 런타임에서는 열 정의 및 기본 키 정보와 같은 테이블 스키마를 기반으로 기본 Insert, Update 및 Delete 문을 만듭니다. 기본 동작을 사용하지 않으려면 업데이트 동작을 구성하고 데이터베이스의 데이터 작업에 필요한 삽입, 업데이트 및 삭제를 수행하기 위한 특정 저장 프로시저를 지정할 수 있습니다. 엔터티 클래스가 뷰에 매핑되는 때와 같이 기본 동작이 생성되지 않은 경우에도 이렇게 할 수 있습니다. 또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다. 자세한 내용은 참조 [사용자 지정 작업에서 사용 하 여 저장 프로시저](/dotnet/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures)합니다.  
  
> [!NOTE]
> 이 연습을 수행 하려면의 **InsertCustomer**, **UpdateCustomer**, 및 **DeleteCustomer** Northwind 데이터베이스에 대 한 프로시저를 저장 합니다.  
  
이 연습에서는 저장 프로시저를 사용하여 데이터를 데이터베이스에 다시 저장하기 위한 기본 LINQ to SQL 런타임 동작을 재정의하는 단계에 대해 설명합니다.  
  
이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   새 Windows Forms 응용 프로그램을 만들고 여기에 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 파일을 추가합니다.  
  
-   Northwind Customers 테이블에 매핑되는 엔터티 클래스를 만듭니다.  
  
-   LINQ to SQL Customer 클래스를 참조하는 개체 데이터 소스를 만듭니다.  
  
-   Customer 클래스에 바인딩된 <xref:System.Windows.Forms.DataGridView>를 포함하는 Windows Form을 만듭니다.  
  
-   폼의 저장 기능을 구현합니다.  
  
-   <xref:System.Data.Linq.DataContext>에 저장 프로시저를 추가하여 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 메서드를 만듭니다.  
  
-   저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하도록 Customer 클래스를 구성합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소

이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server 버전의 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
## <a name="creating-an-application-and-adding-linq-to-sql-classes"></a>응용 프로그램 만들기 및 LINQ to SQL 클래스 추가

[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스로 작업하고 데이터를 Windows Form에 표시하므로 새 Windows Forms 응용 프로그램을 만들고 LINQ to SQL 클래스 파일을 추가합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-new-windows-forms-application-project-that-contains-linq-to-sql-classes"></a>LINQ to SQL 클래스에 포함 된 새 Windows Forms 응용 프로그램 프로젝트를 만들려면
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **UpdatingWithSProcsWalkthrough**를 선택한 후 **확인**합니다. 
  
     **UpdatingWithSProcsWalkthrough** 프로젝트 생성 되며에 추가할 **솔루션 탐색기**합니다.  
  
4.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
5.  클릭는 **LINQ to SQL 클래스** 템플릿의 **Northwind.dbml** 에 **이름** 상자입니다.  
  
6.  **추가**를 클릭합니다.  
  
     빈 LINQ to SQL 클래스 파일(Northwind.dbml)이 프로젝트에 추가되고 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]가 열립니다.  
  
## <a name="creating-the-customer-entity-class-and-object-data-source"></a>Customer 엔터티 클래스 및 개체 데이터 소스 만들기

만들 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 매핑되는 데이터베이스 테이블에서 테이블을 끌어 클래스 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 그러면 데이터베이스의 테이블에 매핑되는 LINQ to SQL 엔터티 클래스가 생성됩니다. 엔터티 클래스를 만든 후 이 클래스를 공용 속성이 있는 다른 클래스처럼 개체 데이터 소스로 사용할 수 있습니다.  
  
### <a name="to-create-a-customer-entity-class-and-configure-a-data-source-with-it"></a>Customer 엔터티 클래스를 만들고 이 클래스를 사용하여 데이터 소스를 구성하려면
  
1.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 샘플 데이터베이스의 SQL Server 버전에서 고객 테이블을 찾습니다. 
  
2.  끌어서는 **고객** 에서 노드 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 화면입니다.  
  
     라는 엔터티 클래스가 **고객** 만들어집니다. 이 클래스에는 Customers 테이블의 열에 해당하는 속성이 있습니다. 엔터티 클래스 이름이 **고객** (하지 **고객**) Customers 테이블의 단일 고객을 나타내기 때문입니다.  
  
    > [!NOTE]
    >  이러한 이름 바꾸기 동작 이라고 *복수 적용*합니다. 설정할 수 있습니다 설정 하거나 해제는 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)합니다. 자세한 내용은 참조 [하는 방법: 복수형 설정 및 해제 (O/R 디자이너)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md)합니다.  
  
3.  에 **빌드** 메뉴를 클릭 **UpdatingwithSProcsWalkthrough 빌드** 프로젝트를 빌드합니다.  
  
4.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
5.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.  
  
6.  클릭 **개체** 에 **데이터 소스 형식 선택** 페이지 한 다음 클릭 **다음**합니다.  
  
7.  확장 된 **UpdatingwithSProcsWalkthrough** 노드 찾아 선택 하 고는 **고객** 클래스.  
  
    > [!NOTE]
    >  경우는 **고객** 클래스를 사용할 수 없는 경우, 마법사를 취소 합니다. 프로젝트를 빌드할 및 마법사를 다시 실행 합니다.  
8.  클릭 **마침** 데이터 소스를 만들고 추가 하는 **고객** 엔터티 클래스를는 **데이터 소스** 창.  
  
## <a name="creating-a-datagridview-to-display-the-customer-data-on-a-windows-form"></a>Windows Form에 고객 데이터를 표시하기 위해 DataGridView 만들기

끌어와 서 엔터티 클래스에 바인딩된 컨트롤을 만들 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 데이터 소스 항목의 **데이터 소스** 창에서 Windows Form으로 합니다.  
  
### <a name="to-add-controls-that-are-bound-to-the-entity-classes"></a>엔터티 클래스에 바인딩된 컨트롤을 추가하려면
  
1.  디자인 뷰에서 Form1을 엽니다.  
  
2.  **데이터 원본** 끌어 창에서 **고객** Form1으로 노드.  
  
    > [!NOTE]
    > 표시 하는 **데이터 원본** 창 클릭 **데이터 소스 표시** 에 **데이터** 메뉴.  
  
3.  코드 편집기에서 Form1을 엽니다.  
  
4.  폼에서 특정 메서드의 외부이지만 Form1 클래스의 내부인 위치에 다음 코드를 폼에 대해 전역적으로 추가합니다.  
  
    ```vb  
    Private NorthwindDataContext1 As New NorthwindDataContext  
    ```  
  
    ```csharp  
    private NorthwindDataContext northwindDataContext1  
        = new NorthwindDataContext();    
    ```  
  
5.  `Form_Load` 이벤트에 대한 이벤트 처리기를 만들고 다음 코드를 처리기에 추가합니다.  
  
    ```vb  
    CustomerBindingSource.DataSource = NorthwindDataContext1.Customers  
    ```  
  
    ```csharp  
    customerBindingSource.DataSource  
        = northwindDataContext1.Customers;    
    ```  
  
## <a name="implementing-save-functionality"></a>저장 기능 구현

기본적으로 저장 단추를 사용할 수 없으며 저장 기능이 구현되지 않습니다. 또한 개체 데이터 소스에 대해 데이터 바인딩된 컨트롤을 만들 때 변경된 데이터를 데이터베이스에 저장하는 코드가 자동으로 추가되지 않습니다. 이 단원에서는 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 개체에서 저장 단추를 사용하고 저장 기능을 구현하는 방법에 대해 설명합니다.  
  
### <a name="to-implement-save-functionality"></a>저장 기능을 구현하려면
  
1.  디자인 뷰에서 Form1을 엽니다.  
  
2.  저장 선택 단추는 **CustomerBindingNavigator** (플로피 디스크 아이콘이 있는 단추).  
  
3.  에 **속성** 창의 설정는 **Enabled** 속성을 **True**합니다.  
  
4.  저장 단추를 두 번 클릭하여 이벤트 처리기를 만들고 코드 편집기로 전환합니다.  
  
5.  저장 단추 이벤트 처리기에 다음 코드를 추가합니다.  
  
    ```vb  
    NorthwindDataContext1.SubmitChanges()  
    ```  
  
    ```csharp  
    northwindDataContext1.SubmitChanges();  
    ```  
  
## <a name="overriding-the-default-behavior-for-performing-updates-inserts-updates-and-deletes"></a>업데이트(삽입, 업데이트 및 삭제)를 수행하기 위한 기본 동작 재정의
  
### <a name="to-override-the-default-update-behavior"></a>기본 업데이트 동작을 재정의하려면
  
1.  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 LINQ to SQL 파일을 엽니다. (두 번 클릭 하 고 **Northwind.dbml** 파일을 **솔루션 탐색기**.)  
  
2.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스를 확장 **Stored Procedures** 노드를 찾습니다는  **InsertCustomers**, **UpdateCustomers**, 및 **DeleteCustomers** 저장 프로시저입니다.  
  
3.  세 개의 저장 프로시저를 모두 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 끌어 옵니다.  
  
     이러한 저장 프로시저가 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다. 자세한 내용은 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
4.  선택 된 **고객** 엔터티 클래스에는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.  
  
5.  에 **속성** 창에서는 **삽입** 속성입니다.  
  
6.  옆에 있는 줄임표 (...) **런타임 사용** 열려는 **동작 구성** 대화 상자.  
  
7.  선택 **사용자 지정**합니다.  
  
8.  선택 된 **InsertCustomers** 에서 메서드는 **사용자 지정** 목록입니다.  
  
9. 클릭 **적용** 선택한 클래스 및 동작에 대 한 구성을 저장 합니다.  
  
    > [!NOTE]
    >  계속 클릭으로 각 클래스/동작 조합에 대 한 동작을 구성할 수 있습니다 **적용** 각 변경 합니다. 클릭 하기 전에 클래스 또는 동작을 변경 하는 경우 **적용**, 변경 내용을 적용 하려면 나타납니다 묻는 경고 대화 상자가 있습니다.  
  
10. 선택 **업데이트** 에 **동작** 목록입니다.  
  
11. 선택 **사용자 지정**합니다.  
  
12. 선택 된 **UpdateCustomers** 에서 메서드는 **사용자 지정** 목록입니다.  
  
     목록을 살펴보고 **메서드 인수** 및 **클래스 속성** 두는 및 **메서드 인수** 와 두 개의 **클래스 속성**테이블의 일부 열에 대 한 합니다. 이를 사용하면 손쉽게 변경 내용을 추적하고 동시성 위반을 확인하는 문을 만들 수 있습니다.  
  
13. 지도 **Original_CustomerID** 메서드 인수를는 **CustomerID (Original)** 클래스 속성입니다.  
  
    > [!NOTE]
    >  기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다. 속성 이름이 변경되거나 더 이상 테이블 및 엔터티 클래스 간에 일치하지 않아 O/R 디자이너에서 올바른 매핑을 결정할 수 없는 경우에는 매핑할 해당하는 클래스 속성을 선택해야 합니다. 또한 메서드 인수를 매핑할 올바른 클래스 속성이 없는, 설정할 수 있습니다는 **클래스 속성** 값을 **(없음)**합니다.  
  
14. 클릭 **적용** 선택한 클래스 및 동작에 대 한 구성을 저장 합니다.  
  
15. 선택 **삭제** 에 **동작** 목록입니다.  
  
16. 선택 **사용자 지정**합니다.  
  
17. 선택 된 **DeleteCustomers** 에서 메서드는 **사용자 지정** 목록입니다.  
  
18. 지도 **Original_CustomerID** 메서드 인수를는 **CustomerID (Original)** 클래스 속성입니다.  
  
19. **확인**을 클릭합니다.  
  
> [!NOTE]
> 이 연습에서는 문제가 되지 않지만 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]은 삽입 및 업데이트 과정에서 identity(자동 증분), rowguidcol(데이터베이스에서 생성된 GUID) 및 timestamp 열에 대해 데이터베이스에서 생성된 값을 자동으로 처리한다는 점을 기억할 필요가 있습니다. 데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다. 데이터베이스에서 생성된 값을 반환하려면 수동으로 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 `true`로 설정하고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>를 <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync> 또는 <xref:System.Data.Linq.Mapping.AutoSync> 중 하나로 설정해야 합니다.  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트

다시 확인 하려면 응용 프로그램을 실행는 **UpdateCustomers** 저장된 프로시저는 데이터베이스의 고객 레코드를 제대로 업데이트 합니다.

### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면

1.  F5 키를 누릅니다.  
  
2.  표에서 레코드를 수정하여 업데이트 동작을 테스트합니다.  
  
3.  새 레코드를 추가하여 삽입 동작을 테스트합니다.  
  
4.  저장 단추를 클릭하여 변경 내용을 데이터베이스에 다시 저장합니다.  
  
5.  폼을 닫아 디버깅을  
  
6.  F5 키를 눌러 업데이트된 레코드와 새로 삽입한 레코드가 있는지 확인합니다.  
  
7.  3단계에서 만든 새 레코드를 삭제하여 삭제 동작을 테스트합니다.  
  
8.  저장 단추를 클릭하여 변경 내용을 전송하고 데이터베이스에서 삭제한 레코드를 제거합니다.  
  
9. 폼을 닫아 디버깅을  
  
10. F5 키를 눌러 삭제한 레코드가 데이터베이스에서 제거되었는지 확인합니다.  
  
    > [!NOTE]
    > 응용 프로그램에서의 값에 따라 SQL Server Express Edition을 사용 하는 경우는 **출력 디렉터리로 복사** 데이터베이스 파일의 속성을 10 단계에서 f5 키를 눌러 변경 내용이 표시 되지 않을 수 있습니다.

## <a name="next-steps"></a>다음 단계

응용 프로그램 요구 사항에 따라 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 엔터티 클래스를 만든 후 몇 단계를 더 수행할 수도 있습니다. 이 응용 프로그램에서 개선할 수 있는 몇 가지 사항은 다음과 같습니다.

- 업데이트 동안 동시성 검사를 구현합니다. 자세한 내용은 참조 [낙관적 동시성: 개요](/dotnet/framework/data/adonet/sql/linq/optimistic-concurrency-overview)합니다.

- LINQ 쿼리를 추가하여 데이터를 필터링합니다. 자세한 내용은 참조 [LINQ 쿼리 (C#) 소개](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)합니다.

## <a name="see-also"></a>참고 항목

[LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)(Visual Studio의 LINQ to SQL 도구)  
[DataContext 메서드](../data-tools/datacontext-methods-o-r-designer.md)  
[방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제를 수행 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)  
[LINQ to SQL 쿼리](/dotnet/framework/data/adonet/sql/linq/linq-to-sql-queries)