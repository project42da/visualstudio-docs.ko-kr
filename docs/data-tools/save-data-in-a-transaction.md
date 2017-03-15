---
title: "연습: 트랜잭션에 데이터 저장 | Microsoft Docs"
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
  - "데이터[Visual Studio], 트랜잭션에 저장"
  - "데이터 저장"
  - "System.Transactions 네임스페이스"
  - "Transactions 네임스페이스"
  - "트랜잭션, 데이터 저장"
ms.assetid: 80260118-08bc-4b37-bfe5-9422ee7a1e4e
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 트랜잭션에 데이터 저장
이 연습에서는 <xref:System.Transactions> 네임스페이스를 사용하여 트랜잭션에서 데이터를 저장하는 방법을 보여줍니다.  이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블을 사용합니다.  
  
## 사전 요구 사항  
 이 연습을 진행하려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.  Northwind 샘플 데이터베이스를 설정하는 방법에 대한 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
## Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 **Windows 응용 프로그램**을 만듭니다.  
  
#### 새 Windows 프로젝트를 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 새 **프로젝트**를 만듭니다.  
  
2.  프로젝트 이름을 SavingDataInATransactionWalkthrough로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **SavingDataInATransactionWalkthrough** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터베이스 데이터 소스 만들기  
 이 단계에서는 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블을 기반으로 하는 데이터 소스를 만듭니다.  
  
#### 데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 선택하여 **연결 추가\/수정** 대화 상자를 시작하고 Northwind 데이터베이스에 대한 연결을 만듭니다.  
  
5.  데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
8.  `Customers` 및 `Orders` 테이블을 선택하고 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 `Customers` 및 `Orders` 테이블이 **데이터 소스** 창에 나타납니다.  
  
## 폼에 컨트롤 추가  
 **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### Windows Form에서 데이터 바인딩된 컨트롤을 만들려면  
  
-   **데이터 소스** 창에서 **Customers** 노드를 확장합니다.  
  
-   주 **Customers** 노드를 **데이터 소스** 창에서 **Form1**로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
-   주 **Orders** 노드가 아닌 관련 **Orders** 노드\(**Fax** 열 아래의 관련 자식 테이블 노드\)를 폼의 **CustomersDataGridView** 아래로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView>가 폼에 나타납니다.  [OrdersTableAdapter](../data-tools/tableadapter-overview.md) 및 <xref:System.Windows.Forms.BindingSource>가 구성 요소 트레이에 표시됩니다.  
  
## System.Transactions 어셈블리에 대한 참조 추가  
 트랜잭션은 <xref:System.Transactions> 네임스페이스를 사용합니다.  system.transactions 어셈블리에 대한 프로젝트 참조는 기본적으로 추가되어 있지 않으므로 수동으로 추가해야 합니다.  
  
#### System.Transactions DLL 파일에 대한 참조를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 선택합니다.  
  
2.  **.NET** 탭에서 **System.Transactions**를 선택하고 **확인**을 클릭합니다.  
  
     **System.Transactions**에 대한 참조가 프로젝트에 추가됩니다.  
  
## BindingNavigator의 SaveItem 단추에 대한 코드 수정  
 기본적으로 폼에 놓는 첫 번째 테이블에 대해 <xref:System.Windows.Forms.BindingNavigator>에 있는 저장 단추의 `click` 이벤트에 코드가 추가됩니다.  추가 테이블을 업데이트하려면 코드를 수동으로 추가해야 합니다.  이 연습에서는 저장 단추의 클릭 이벤트 처리기에서 기존 저장 코드를 리팩터링한 다음 몇 가지 메서드를 추가로 만들어 행의 추가 또는 삭제 필요성에 따른 특정 업데이트 기능을 제공합니다.  
  
#### 자동으로 생성된 저장 코드를 수정하려면  
  
1.  **CustomersBindingNavigator**에서 **저장** 단추\(플로피 디스크 아이콘이 있는 단추\)를 두 번 클릭합니다.  
  
2.  `CustomersBindingNavigatorSaveItem_Click` 메서드를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbRaddataSaving#4](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_1.vb)]
     [!code-cs[VbRaddataSaving#4](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_1.cs)]  
  
 관련 데이터의 변경을 조정하는 순서는 다음과 같습니다.  
  
-   자식 레코드를 삭제합니다. 여기서는 `Orders` 테이블에서 레코드를 삭제합니다.  
  
-   부모 레코드를 삭제합니다. 여기서는 `Customers` 테이블에서 레코드를 삭제합니다.  
  
-   부모 레코드를 삽입합니다. 여기서는 `Customers` 테이블에 레코드를 삽입합니다.  
  
-   자식 레코드를 삽입합니다. 여기서는 `Orders` 테이블에 레코드를 삽입합니다.  
  
#### 기존 주문을 삭제하려면  
  
-   다음 `DeleteOrders` 메서드를 **Form1**에 추가합니다.  
  
     [!code-vb[VbRaddataSaving#5](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_2.vb)]
     [!code-cs[VbRaddataSaving#5](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_2.cs)]  
  
#### 기존 고객을 삭제하려면  
  
-   다음 `DeleteCustomers` 메서드를 **Form1**에 추가합니다.  
  
     [!code-vb[VbRaddataSaving#6](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_3.vb)]
     [!code-cs[VbRaddataSaving#6](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_3.cs)]  
  
#### 새 고객을 추가하려면  
  
-   다음 `AddNewCustomers` 메서드를 **Form1**에 추가합니다.  
  
     [!code-vb[VbRaddataSaving#7](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_4.vb)]
     [!code-cs[VbRaddataSaving#7](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_4.cs)]  
  
#### 새 주문을 추가하려면  
  
-   다음 `AddNewOrders` 메서드를 **Form1**에 추가합니다.  
  
     [!code-vb[VbRaddataSaving#8](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_5.vb)]
     [!code-cs[VbRaddataSaving#8](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_5.cs)]  
  
## 응용 프로그램 실행  
  
#### 응용 프로그램을 실행하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
## 참고 항목  
 [트랜잭션 및 동시성](../Topic/Transactions%20and%20Concurrency.md)   
 [Oracle 분산 트랜잭션](../Topic/Oracle%20Distributed%20Transactions.md)   
 [방법: 트랜잭션을 사용하여 데이터 저장](../data-tools/save-data-by-using-a-transaction.md)   
 [SQL Server와의 System.Transactions 통합](../Topic/System.Transactions%20Integration%20with%20SQL%20Server.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)