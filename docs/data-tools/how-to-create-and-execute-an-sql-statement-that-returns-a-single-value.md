---
title: "방법: 단일 값을 반환하는 SQL 문 만들기 및 실행 | Microsoft Docs"
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
  - "데이터 명령, 스칼라 값 반환"
  - "데이터 판독기"
  - "DataReader 개체"
  - "스칼라 값"
  - "SQL 문, 데이터 명령"
  - "저장 프로시저, 단일 값 반환"
ms.assetid: eb366496-69e5-4462-8683-653054165c5c
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 단일 값을 반환하는 SQL 문 만들기 및 실행
단일 값을 반환하는 SQL 문을 실행하려면 SQL 문을 실행하도록 구성된 TableAdapter 쿼리\(예: `CustomersTableAdapter.CustomerCount()`\)를 실행하면 됩니다.  
  
 응용 프로그램에서 TableAdapter를 사용하지 않으면 명령 개체에서 `ExecuteScalar` 메서드를 호출하여 `CommandType` 속성을 <xref:System.Data.CommandType>로 설정합니다.  \("명령 개체"는 응용 프로그램에서 사용하고 있는 [.NET Framework Data Provider](../Topic/.NET%20Framework%20Data%20Providers.md)의 특정 명령을 참조합니다.  예를 들어, 응용 프로그램에서 .NET Framework Data Provider for SQL Server를 사용하고 있으면 명령 개체는 <xref:System.Data.SqlClient.SqlCommand>가 됩니다.  
  
 다음 예제에서는 TableAdapter 또는 명령 개체를 사용하여 데이터베이스에서 단일 값을 반환하는 SQL 문을 실행하는 방법을 보여 줍니다.  명령과 TableAdapter를 사용하여 쿼리하는 방법에 대한 자세한 내용은 [데이터로 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## TableAdapter를 사용하여 단일 값을 반환하는 SQL 문 실행  
 이 예제에서는 [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)를 사용하여 TableAdapter 쿼리를 만드는 방법을 보여 주고, TableAdapter의 인스턴스를 선언하고 쿼리를 실행하는 방법에 대해 설명합니다.  
  
#### TableAdapter를 사용하여 단일 값을 반환하는 SQL 문을 만들려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)를 참조하십시오.  
  
2.  TableAdapter가 없으면 새로 만듭니다.  TableAdapter를 만드는 방법에 대한 자세한 내용은 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)를 참조하십시오.  
  
3.  TableAdapter에 SQL 문을 사용하여 단일 값을 반환하는 쿼리가 이미 있으면 다음의 "TableAdapter의 인스턴스를 선언하고 쿼리를 실행하려면" 단계로 건너뜁니다. 그렇지 않으면 4단계를 계속하여 단일 값을 반환하는 쿼리를 새로 만듭니다.  
  
4.  원하는 TableAdapter를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴를 사용하여 쿼리를 추가합니다.  
  
     **TableAdapter 쿼리 구성 마법사**가 열립니다.  
  
5.  **SQL 문 사용**의 기본값을 그대로 두고 **다음**을 클릭합니다.  
  
6.  **단일 값을 반환하는 SELECT** 옵션을 선택하고 **다음**을 클릭합니다.  
  
7.  SQL 문을 입력하거나 **쿼리 작성기**를 사용하여 SQL 문을 만들고 **다음**을 클릭합니다.  
  
8.  쿼리의 이름을 제공합니다.  
  
9. 마법사를 완료합니다. 쿼리가 TableAdapter에 추가됩니다.  
  
10. 프로젝트를 빌드합니다.  
  
#### TableAdapter의 인스턴스를 선언하고 쿼리를 실행하려면  
  
1.  실행할 쿼리가 포함된 TableAdapter의 인스턴스를 선언합니다.  
  
    -   디자인 타임 도구를 사용하여 인스턴스를 만들려면 **도구 상자**에서 원하는 TableAdapter를 끕니다.  프로젝트의 구성 요소는 이제 **도구 상자**에서 프로젝트 이름과 일치하는 제목 아래에 나타납니다. TableAdapter가 **도구 상자**에 나타나지 않으면 프로젝트를 빌드해야 할 수도 있습니다.  
  
         또는  
  
    -   코드에서 인스턴스를 만들려면 다음 코드를 TableAdapter와 <xref:System.Data.DataSet>의 이름으로 바꿉니다.  
  
         `Dim tableAdapter As New DataSetTableAdapters.TableAdapter`  
  
        > [!NOTE]
        >  TableAdapter는 연결된 데이터 집합 클래스 안에 없습니다.  각 데이터 집합은 자체 네임스페이스에 해당 TableAdapter 컬렉션을 갖습니다.  예를 들어, `SalesDataSet`이라는 데이터 집합이 있으면 해당 TableAdapter가 포함된 `SalesDataSetTableAdapters` 네임스페이스가 있습니다.  
  
2.  코드에서 다른 메서드를 호출하는 것처럼 쿼리를 호출합니다.  쿼리는 TableAdapter의 메서드입니다.  다음 코드를 쿼리 및 TableAdapter의 이름으로 바꿉니다.  쿼리에 필요한 매개 변수를 전달하고 반환 값을 사용하여 다른 작업\(예: 변수에 할당\)을 수행해야 할 수도 있습니다.  쿼리에 매개 변수가 필요한지 여부 또는 어떤 매개 변수가 필요한지 확실히 모르면 IntelliSense를 검사하여 쿼리의 필요한 시그니처를 확인합니다.  쿼리에서 매개 변수를 사용하는지 여부에 따라 코드가 다음 예제 중 하나와 비슷할 수 있습니다.  
  
     `TableAdapter.Query()`  
  
     `TableAdapter.Query(Parameters)`  
  
3.  쿼리에서 반환된 값을 변수에 할당해야 할 수도 있습니다.  단일 값을 반환하는 TableAdapter 쿼리는 개체를 반환하는 `ExecuteScalar` 메서드와는 달리 쿼리를 기반으로 데이터 형식을 반환합니다.  예를 들어, TableAdapter 쿼리가 데이터 형식이 정수인 단일 열을 선택하면 쿼리의 반환 값은 정수입니다.  열에서 null 값을 허용하면 반환 값은 null 허용 형식 중 하나\(예: `Nullable(Of Integer)`\)가 됩니다.  null 허용 형식에 대한 자세한 내용은 <xref:System.Nullable>을 참조하십시오.  TableAdapter의 인스턴스를 선언하고 쿼리를 실행하는 전체 코드는 다음과 같습니다. 이 예제에서는 반환 값이 정수라고 가정하므로 실제 쿼리에서 반환되는 데이터 형식에 따라 코드를 조정하십시오.  
  
     [!code-cs[VbRaddataFillingAndExecuting#9](../data-tools/codesnippet/CSharp/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value_1.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#9](../data-tools/codesnippet/VisualBasic/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value_1.vb)]  
  
## 명령 개체를 사용하여 단일 값을 반환하는 SQL 문 실행  
 다음 예제에서는 명령을 만들고 단일 값을 반환하는 SQL 문을 실행하는 방법을 보여 줍니다.  명령의 매개 변수 값을 설정하고 가져오는 방법에 대한 자세한 내용은 [방법: 명령 개체의 매개 변수 설정 및 가져오기](../Topic/How%20to:%20Set%20and%20Get%20Parameters%20for%20Command%20Objects.md)를 참조하십시오.  
  
 이 예제에서는 <xref:System.Data.SqlClient.SqlCommand> 개체를 사용하며 다음이 필요합니다.  
  
-   <xref:System>, <xref:System.Data> 및 <xref:System.Xml> 네임스페이스에 대한 참조  
  
-   `SqlConnection1`이라는 데이터 연결  
  
-   `SqlConnection1`이 연결된 데이터 소스의 `Customers`라는 테이블  \(그렇지 않으면, 데이터 소스에 대한 유효한 SQL 문이 필요\)  
  
#### DataCommand를 사용하여 단일 값을 반환하는 SQL 문을 실행하려면  
  
-   코드를 실행할 메서드에 다음 코드를 추가합니다.  명령의 `ExecuteScalar` 메서드를 호출하여 단일 값을 반환합니다\(예: <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>\).  데이터는 <xref:System.Object>에 반환됩니다.  
  
     [!code-cs[VbRaddataFillingAndExecuting#10](../data-tools/codesnippet/CSharp/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value_2.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#10](../data-tools/codesnippet/VisualBasic/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value_2.vb)]  
  
## .NET Framework 보안  
 응용 프로그램에는 데이터베이스에 액세스하고 SQL 문을 실행할 수 있는 권한이 필요합니다.  
  
## 참고 항목  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.OleDb.OleDbCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.Odbc.OdbcCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.OracleClient.OracleCommand.ExecuteScalar%2A?displayProperty=fullName>   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)   
 [방법: 데이터 집합을 데이터로 채우기](../data-tools/how-to-fill-a-dataset-with-data.md)   
 [데이터로 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [방법: 명령 개체의 매개 변수 설정 및 가져오기](../Topic/How%20to:%20Set%20and%20Get%20Parameters%20for%20Command%20Objects.md)