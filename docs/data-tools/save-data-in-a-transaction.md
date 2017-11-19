---
title: "연습: 트랜잭션에 데이터 저장 | Microsoft Docs"
ms.custom: 
ms.date: 09/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System.Transactions namespace
- data [Visual Studio], saving in a transaction
- transactions, saving data
- Transactions namespace
- saving data
ms.assetid: 80260118-08bc-4b37-bfe5-9422ee7a1e4e
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f8d1d25c2aaa66658df53dbaea366c196e8e7f6b
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="walkthrough-save-data-in-a-transaction"></a>연습: 트랜잭션에 데이터 저장
이 연습에서는 사용 하 여 트랜잭션에서 데이터를 저장 하는 방법을 보여 줍니다.는 <xref:System.Transactions> 네임 스페이스입니다. 이 연습에서는 Windows Forms 응용 프로그램을 만들어야 합니다. Northwind 샘플 데이터베이스의 두 테이블에 대 한 데이터 집합을 만들려면 데이터 소스 구성 마법사를 사용 합니다. 데이터 바인딩된 컨트롤을 Windows form 및 수정 하면서 간단한 BindingNavigator의 저장 단추는 TransactionScope 내에서 데이터베이스를 업데이트 하려면에 대 한 코드를 추가 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server 버전의 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **.NET 데스크톱 개발** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
## <a name="create-a-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기  
 첫 번째 단계를 만드는 것을 **Windows Forms 응용 프로그램**합니다.  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **SavingDataInATransactionWalkthrough**를 선택한 후 **확인**합니다. 
  
     **SavingDataInATransactionWalkthrough** 프로젝트를 만들고 추가 **솔루션 탐색기**합니다.  
  
## <a name="create-a-database-data-source"></a>데이터베이스 데이터 소스 만들기  
 이 단계는 **데이터 소스 구성 마법사** 기반으로 데이터 원본을 만들려면는 `Customers` 및 `Orders` Northwind 예제 데이터베이스의 테이블입니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
3.  에 **데이터 소스 형식 선택** 화면에서 **데이터베이스**를 선택한 후 **다음**합니다.  
  
4.  에 **데이터 연결 선택** 화면에서 다음 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자 및 Northwind 데이터베이스에 연결을 만듭니다.  
  
5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 선택 옵션을 선택 **다음**합니다.  
  
6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 화면에서 **다음**합니다.  
  
7.  에 **데이터베이스 개체 선택** 화면에서 확장 된 **테이블** 노드.  
  
8.  선택 된 `Customers` 및 `Orders` 테이블을 선택한 다음 선택 **마침**합니다.  
  
     **NorthwindDataSet** 프로젝트에 추가 및 `Customers` 및 `Orders` 에 테이블이 나타나는 **데이터 소스** 창.  
  
## <a name="add-controls-to-the-form"></a>폼에 컨트롤 추가  
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다는 **데이터 소스** 창에서 폼으로 합니다.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>바인딩된 Windows form의 컨트롤에 데이터를 만들려면  
  
-   에 **데이터 원본** 창 확장는 **고객** 노드.  
  
-   주 끌어 **고객** 에서 노드는 **데이터 원본** 창으로 **Form1**합니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
-   관련 끌어 **Orders** 노드 (주 **Orders** 관련된 자식 테이블 노드 아래의 있지만 노드를는 **팩스** 열) 아래 양식으로는  **CustomersDataGridView**합니다.  
  
     <xref:System.Windows.Forms.DataGridView>가 폼에 나타납니다. `OrdersTableAdapter` 및 <xref:System.Windows.Forms.BindingSource> 구성 요소 트레이에 나타납니다.  
  
## <a name="add-a-reference-to-the-systemtransactions-assembly"></a>System.Transactions 어셈블리에 대 한 참조를 추가 합니다.  
 트랜잭션은 <xref:System.Transactions> 네임스페이스를 사용합니다. system.transactions 어셈블리에 대한 프로젝트 참조는 기본적으로 추가되어 있지 않으므로 수동으로 추가해야 합니다.  
  
#### <a name="to-add-a-reference-to-the-systemtransactions-dll-file"></a>System.Transactions DLL 파일에 대한 참조를 추가하려면  
  
1.  에 **프로젝트** 메뉴 선택 **참조 추가**합니다.  
  
2.  선택 **System.Transactions** (에 **.NET** 탭)을 선택한 후 **확인**합니다.  
  
     에 대 한 참조 **System.Transactions** 프로젝트에 추가 합니다.  
  
## <a name="modify-the-code-in-the-bindingnavigators-saveitem-button"></a>BindingNavigator의 SaveItem 단추에 코드를 수정 합니다.  
 폼에 놓는 첫 번째 테이블에 대 한 코드에는 기본적으로 추가 됩니다는 `click` 이벤트 저장 단추는 <xref:System.Windows.Forms.BindingNavigator>합니다. 추가 테이블을 업데이트하려면 코드를 수동으로 추가해야 합니다. 이 연습에서는 리팩터링한 기존 저장 코드 저장 단추의 클릭 이벤트 처리기입니다. 행 추가 또는 삭제 필요성에 따른 특정 업데이트 기능을 제공 하는 몇 가지 더 많은 메서드를 만들 수도 있습니다.  
  
#### <a name="to-modify-the-auto-generated-save-code"></a>자동으로 생성된 저장 코드를 수정하려면  
  
1.  선택 된 **저장** 단추는 **CustomersBindingNavigator** (플로피 디스크 아이콘이 있는 단추).  
  
2.  `CustomersBindingNavigatorSaveItem_Click` 메서드를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbRaddataSaving#4](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#4](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_1.cs)]  
  
관련 데이터의 변경을 조정하는 순서는 다음과 같습니다.  
  
-   자식 레코드를 삭제 합니다. (이 경우 레코드를 삭제는 `Orders` 테이블입니다.)  
  
-   부모 레코드를 삭제 합니다. (이 경우 레코드를 삭제는 `Customers` 테이블입니다.)  
  
-   부모 레코드를 삽입 합니다. (이 경우에 레코드를 삽입는 `Customers` 테이블입니다.)  
  
-   자식 레코드를 삽입 합니다. (이 경우에 레코드를 삽입는 `Orders` 테이블입니다.)  
  
#### <a name="to-delete-existing-orders"></a>기존 주문을 삭제하려면  
  
-   다음 추가 `DeleteOrders` 메서드를 **Form1**:  
  
     [!code-vb[VbRaddataSaving#5](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_2.vb)]
     [!code-csharp[VbRaddataSaving#5](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_2.cs)]  
  
#### <a name="to-delete-existing-customers"></a>기존 고객을 삭제하려면  
  
-   다음 추가 `DeleteCustomers` 메서드를 **Form1**:  
  
     [!code-vb[VbRaddataSaving#6](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_3.vb)]
     [!code-csharp[VbRaddataSaving#6](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_3.cs)]  
  
#### <a name="to-add-new-customers"></a>새 고객을 추가하려면  
  
-   다음 추가 `AddNewCustomers` 메서드를 **Form1**:  
  
     [!code-vb[VbRaddataSaving#7](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_4.vb)]
     [!code-csharp[VbRaddataSaving#7](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_4.cs)]  
  
#### <a name="to-add-new-orders"></a>새 주문을 추가하려면  
  
-   다음 추가 `AddNewOrders` 메서드를 **Form1**:  
  
     [!code-vb[VbRaddataSaving#8](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_5.vb)]
     [!code-csharp[VbRaddataSaving#8](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_5.cs)]  
  
## <a name="run-the-application"></a>응용 프로그램 실행  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   선택 **F5** 응용 프로그램을 실행 합니다.  
  
## <a name="see-also"></a>참고 항목
[방법: 트랜잭션을 사용 하 여 데이터 저장](../data-tools/save-data-by-using-a-transaction.md)  
[데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)