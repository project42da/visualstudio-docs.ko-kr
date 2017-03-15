---
title: "연습: 여러 개의 쿼리가 있는 TableAdapter 만들기 | Microsoft Docs"
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
  - "데이터[Visual Studio], TableAdapter"
  - "데이터[Visual Studio], 연습"
  - "쿼리[Visual Studio], TableAdapter"
  - "TableAdapter 쿼리, 만들기"
  - "TableAdapter, 만들기"
ms.assetid: f784dc4d-d514-4ade-8226-f8271c5b1ed8
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: 여러 개의 쿼리가 있는 TableAdapter 만들기
이 연습에서는 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 데이터 집합에서 TableAdapter를 만듭니다.  여기서는 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 내에서 [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)를 사용하여 [TableAdapter](../data-tools/tableadapter-overview.md)에서 두 번째 쿼리를 만드는 프로세스를 진행합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   **데이터 소스 구성 마법사**를 사용하여 데이터 집합을 빌드해 응용 프로그램에서 데이터 소스를 만들고 구성합니다.  
  
-   **데이터 집합 디자이너**에서 새 데이터 집합을 엽니다.  
  
-   **TableAdapter 쿼리 구성 마법사**를 사용하여 TableAdapter에 쿼리를 추가합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스\(SQL Server 또는 Access 버전\) 액세스 권한.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## 새 Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 Windows 응용 프로그램을 만듭니다.  
  
#### 새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  **프로젝트 형식** 창에서 프로그래밍 언어를 선택합니다.  
  
3.  **템플릿** 창에서 **Windows 응용 프로그램**을 클릭합니다.  
  
4.  프로젝트 이름을 `TableAdapterQueriesWalkthrough`로 지정하고 **확인**을 클릭합니다.  
  
     프로젝트가 **솔루션 탐색기**에 추가되고 디자이너에 새 폼이 표시됩니다.  
  
## TableAdapter가 포함된 데이터베이스 데이터 소스 만들기  
 이 단계에서는 **데이터 소스 구성 마법사**를 사용하여 Northwind 샘플 데이터베이스의 `Customers` 테이블을 기반으로 하는 데이터 소스를 만듭니다.  연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.  Northwind 샘플 데이터베이스를 설정하는 방법에 대한 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
#### 데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 선택하여 **연결 추가\/수정** 대화 상자를 시작합니다.  
  
5.  데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
8.  **Customers** 테이블을 선택하고 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 **Customers** 테이블이 **데이터 소스** 창에 나타납니다.  
  
## 데이터 집합 디자이너에서 데이터 집합 열기  
  
#### 데이터 집합 디자이너에서 데이터 집합을 열려면  
  
1.  **데이터 소스** 창에서 **NorthwindDataset**를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **디자이너로 데이터 집합 편집**을 선택합니다.  
  
     NorthwindDataset가 **데이터 집합 디자이너**에서 열립니다.  
  
## CustomersTableAdapter에 두 번째 쿼리 추가  
 지금까지 마법사에서 **Customers** 데이터 테이블 및 **CustomersTableAdapter**가 포함된 데이터 집합을 만들었습니다.  이 연습 섹션에서는 **CustomersTableAdapter**에 두 번째 쿼리를 추가합니다.  
  
#### CustomersTableAdapter에 쿼리를 추가하려면  
  
1.  **도구 상자**의 **데이터 집합** 탭에서 **쿼리**를 **Customers** 테이블로 끌어 옵니다.  
  
     [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)가 열립니다.  
  
2.  **SQL 문 사용**을 선택하고 **다음**을 클릭합니다.  
  
3.  **행을 반환하는 SELECT**를 선택하고 **다음**을 클릭합니다.  
  
4.  다음과 같이 WHERE 절을 쿼리에 추가합니다.  
  
    ```  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax   
    FROM Customers   
    WHERE City = @City  
    ```  
  
    > [!NOTE]
    >  Access 버전의 Northwind를 사용 중인 경우 @City 매개 변수를 물음표로 바꿉니다.  \(`SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE City = ?`\)  
  
5.  **생성할 메서드 선택** 페이지에서 **DataTable 채우기** 메서드의 이름을 `FillByCity`로 지정합니다.  
  
    > [!NOTE]
    >  **DataTable 반환** 메서드는 이 연습에서 사용하지 않으므로 확인란 선택을 취소하거나 기본 이름을 그대로 유지해도 됩니다.  
  
6.  **다음**을 클릭하고 마법사를 완료합니다.  
  
     **FillByCity** 쿼리가 **CustomersTableAdapter**에 추가됩니다.  
  
## 폼에서 추가 쿼리를 실행하는 코드 추가  
  
#### 쿼리를 실행하려면  
  
1.  **솔루션 탐색기**에서 **Form1**을 선택하고 **디자이너 보기**를 클릭합니다.  
  
2.  **Customers** 노드를 **데이터 소스** 창에서 **Form1**로 끌어 옵니다.  
  
3.  **보기** 메뉴에서 **코드**를 선택하여 코드 보기로 변경합니다.  
  
4.  `Form1_Load` 이벤트 처리기의 코드를 다음 코드로 바꿔 `FillByCity` 쿼리를 실행합니다.  
  
     [!code-vb[VbRaddataTableAdapters#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-tableadapter-with-multiple-queries_1.vb)]
     [!code-cs[VbRaddataTableAdapters#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-tableadapter-with-multiple-queries_1.cs)]  
  
## 응용 프로그램 실행  
  
#### 응용 프로그램을 실행하려면  
  
-   F5 키를 누릅니다.  
  
-   `City` 값이 `Seattle`인 고객으로 표가 채워집니다.  
  
## 다음 단계  
  
### 응용 프로그램에 기능을 추가하려면  
  
-   <xref:System.Windows.Forms.TextBox> 컨트롤과 <xref:System.Windows.Forms.Button> 컨트롤을 추가하고 텍스트 상자의 값을 쿼리로 전달합니다.  \(`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, TextBox1.Text)`\).  
  
-   데이터 집합에 있는 데이터 테이블의 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에 유효성 검사 논리를 추가합니다.  자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)을 참조하십시오.  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)