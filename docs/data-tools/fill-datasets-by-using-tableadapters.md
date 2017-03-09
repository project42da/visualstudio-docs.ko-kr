---
title: "데이터로 데이터 집합 채우기 | Microsoft Docs"
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
  - "데이터[Visual Studio], 데이터 집합"
  - "데이터[Visual Studio], 검색"
  - "데이터 검색"
  - "데이터 집합[Visual Basic]"
  - "데이터 집합[Visual Basic], 채우기"
  - "데이터 집합[Visual Basic], 데이터 로드"
  - "데이터 검색"
ms.assetid: 55f3bfbe-db78-4486-add3-c62f49e6b9a0
caps.latest.revision: 32
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터로 데이터 집합 채우기
TableAdapter는 Transact\-SQL 쿼리를 실행하고 데이터 집합을 채우는 일반적인 Visual Studio 메커니즘입니다.  
  
 TableAdapter 또는 명령 개체를 사용하여 데이터 소스에 대해 SQL 문 또는 저장 프로시저를 실행할 수 있습니다\(예: <xref:System.Data.SqlClient.SqlCommand>\).  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 디자인 도구를 사용하여 만든 데이터 집합에 데이터를 로드하려면 TableAdapter를 사용합니다.  프로그래밍 방식으로 만든 데이터 집합에 데이터를 로드하려면 데이터 어댑터를 사용합니다.  응용 프로그램에서 데이터 집합을 사용하지 않는 경우에는 명령 개체를 사용하여 SQL 문 또는 저장 프로시저를 데이터베이스에 대해 직접 실행합니다.  
  
 다음 항목에서는 Visual Studio에서 데이터로 데이터 집합을 채우는 데 대한 세부 정보를 제공합니다.  
  
|항목|설명|  
|--------|--------|  
|[방법: 데이터 집합을 데이터로 채우기](../data-tools/how-to-fill-a-dataset-with-data.md)|TableAdapter 및 DataAdapter를 사용하여 데이터 집합에 데이터를 로드하는 방법을 자세히 설명합니다.|  
|[방법: 행을 반환하는 SQL 문 만들기 및 실행](../Topic/How%20to:%20Create%20and%20Execute%20an%20SQL%20Statement%20that%20Returns%20Rows.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 행을 반환하는 SQL 문을 만들고 실행하는 방법을 자세히 설명합니다.|  
|[방법: 단일 값을 반환하는 SQL 문 만들기 및 실행](../data-tools/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 단일 값을 반환하는 SQL 문을 만들고 실행하는 방법을 자세히 설명합니다.|  
|[방법: 값을 반환하지 않는 SQL 문 만들기 및 실행](../data-tools/how-to-create-and-execute-an-sql-statement-that-returns-no-value.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 값을 반환하지 않는 SQL 문을 만들고 실행하는 방법을 자세히 설명합니다.|  
|[방법: 행을 반환하는 저장 프로시저 실행](../Topic/How%20to:%20Execute%20a%20Stored%20Procedure%20that%20Returns%20Rows.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 행을 반환하는 저장 프로시저를 실행하는 방법을 자세히 설명합니다.|  
|[방법: 단일 값을 반환하는 저장 프로시저 실행](../data-tools/how-to-execute-a-stored-procedure-that-returns-a-single-value.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 단일 값을 반환하는 저장 프로시저를 실행하는 방법을 자세히 설명합니다.|  
|[방법: 값을 반환하지 않는 저장 프로시저 실행](../data-tools/how-to-execute-a-stored-procedure-that-returns-no-value.md)|TableAdapter 쿼리 및 Command 개체를 사용하여 값을 반환하지 않는 저장 프로시저를 실행하는 방법을 자세히 설명합니다.|  
|[방법: 명령 개체의 매개 변수 설정 및 가져오기](../Topic/How%20to:%20Set%20and%20Get%20Parameters%20for%20Command%20Objects.md)|쿼리 및 저장 프로시저의 매개 변수에 값을 할당하는 방법과 실행된 명령에서 반환된 매개 변수의 값을 읽는 방법을 자세히 설명합니다.|  
|[연습: 데이터로 데이터 집합 채우기](../Topic/Walkthrough:%20Filling%20a%20Dataset%20with%20Data.md)|데이터 집합을 만들고 데이터베이스의 데이터로 채우는 방법을 자세히 설명합니다.|  
|[연습: XML 데이터를 데이터 집합으로 읽어 오기](../data-tools/read-xml-data-into-a-dataset.md)|데이터 집합에 XML 데이터를 로드한 다음 <xref:System.Windows.Forms.DataGridView> 컨트롤에 데이터 집합을 표시하는 Windows 응용 프로그램을 만드는 방법을 자세히 설명합니다.|  
  
## 데이터 집합 채우기  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디자인 타임 도구\(예: [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 또는 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)\)를 사용하여 데이터 집합을 만드는 경우 TableAdapter를 사용하여 해당 데이터 집합을 채웁니다.  TableAdapter에서 SQL 문 또는 저장 프로시저를 실행합니다.  
  
 디자인 타임 도구를 사용하지 않고 데이터 집합을 만드는 경우에는 데이터 어댑터를 사용하여 데이터를 채우고 업데이트해야 합니다.  TableAdapter는 [.NET Framework 4.6 및 4.5](../Topic/.NET%20Framework%204.6%20and%204.5.md)의 실제 클래스가 아니므로 디자인 타임 도구를 사용하지 않고 만든 데이터 집합 작업에는 적합하지 않습니다.  TableAdapter 또는 데이터 어댑터를 사용하여 데이터를 데이터 집합으로 로드하는 방법에 대한 자세한 내용은 [방법: 데이터 집합을 데이터로 채우기](../data-tools/how-to-fill-a-dataset-with-data.md)를 참조하십시오.  
  
## TableAdapter 쿼리  
 TableAdapter 쿼리를 실행하여 데이터 집합에 데이터를 채울 수 있습니다. 더 구체적으로는 데이터 집합을 구성하는 DataTable에 데이터를 로드합니다.  **데이터 집합 디자이너**에서 [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)를 사용하여 TableAdapter 쿼리를 만들 수 있습니다.  TableAdapter 쿼리는 TableAdapter에 명명된 메서드로 나타나며 TableAdapter 메서드를 호출하여 실행됩니다.  TableAdapter 쿼리의 작성과 실행에 대한 자세한 내용은 다음 페이지를 참조하십시오.  
  
-   [방법: 행을 반환하는 SQL 문 만들기 및 실행](../Topic/How%20to:%20Create%20and%20Execute%20an%20SQL%20Statement%20that%20Returns%20Rows.md)  
  
-   [방법: 단일 값을 반환하는 SQL 문 만들기 및 실행](../data-tools/how-to-create-and-execute-an-sql-statement-that-returns-a-single-value.md)  
  
-   [방법: 값을 반환하지 않는 SQL 문 만들기 및 실행](../data-tools/how-to-create-and-execute-an-sql-statement-that-returns-no-value.md)  
  
-   [방법: 행을 반환하는 저장 프로시저 실행](../Topic/How%20to:%20Execute%20a%20Stored%20Procedure%20that%20Returns%20Rows.md)  
  
-   [방법: 단일 값을 반환하는 저장 프로시저 실행](../data-tools/how-to-execute-a-stored-procedure-that-returns-a-single-value.md)  
  
-   [방법: 값을 반환하지 않는 저장 프로시저 실행](../data-tools/how-to-execute-a-stored-procedure-that-returns-no-value.md)  
  
## Command 개체  
 Command 개체를 사용하면 <xref:System.Data.DataSet>, TableAdapter 또는 <xref:System.Data.Common.DataAdapter> 없이도 데이터베이스에 대해 직접 SQL 문 및 저장 프로시저를 실행할 수 있습니다.  *Command 개체*라는 용어는 응용 프로그램에서 사용하고 있는 .NET Framework Data Provider의 특정 명령을 가리킵니다.  예를 들어, 응용 프로그램에서 .NET Framework Data Provider for SQL Server를 사용하고 있으면 명령 개체는 <xref:System.Data.SqlClient.SqlCommand>가 됩니다.  
  
 데이터 명령의 `CommandType` 속성을 <xref:System.Data.IDbCommand.CommandType%2A> 열거형의 값 중 하나로 설정하면 데이터를 쿼리할 때 SQL 문을 사용할지 아니면 저장 프로시저를 사용할지 구성할 수 있습니다.  SQL 문을 실행하려면 `CommandType`을 <xref:System.Data.CommandType>로 설정하고 저장 프로시저를 실행하려면 <xref:System.Data.CommandType>로 설정합니다.  그런 다음 `CommandText` 속성을 SQL 문 또는 저장 프로시저의 이름으로 설정합니다.  그리고 데이터 명령의 실행 메서드\(`ExecuteReader`, `ExecuteScalar`, `ExecuteNonQuery`\) 중 하나를 호출하여 데이터 명령을 실행할 수 있습니다.  
  
 각 [.NET Framework 데이터 공급자](../Topic/.NET%20Framework%20Data%20Providers.md)에서는 특정 데이터베이스에 최적화된 명령 개체를 제공합니다.  
  
 데이터 명령을 사용하면 응용 프로그램에서 다음 작업을 수행할 수 있습니다.  
  
-   결과를 데이터 집합에 로드하지 않고 직접 읽을 수 있도록 반환하는 Select 명령을 실행합니다.  결과를 읽으려면 컨트롤을 바인딩할 수 있는 정방향의 읽기 전용 커서처럼 작동하는 데이터 판독기\(<xref:System.Data.OleDb.OleDbDataReader>, <xref:System.Data.SqlClient.SqlDataReader>, <xref:System.Data.Odbc.OdbcDataReader> 또는 <xref:System.Data.OracleClient.OracleDataReader> 개체\)를 사용합니다.  이 방법은 메모리 사용을 줄이고 읽기 전용 데이터를 매우 빠르게 로드하는 데 유용합니다.  
  
-   DDL\(Database Definition Language\) 명령을 실행하여 테이블, 저장 프로시저 및 기타 데이터베이스 구조를 작성, 편집 및 제거할 수 있습니다.  이 경우 이러한 작업을 수행하기 위한 권한이 필요합니다.  
  
-   명령을 실행하여 데이터베이스 카탈로그 정보를 얻을 수 있습니다.  
  
-   데이터 집합 테이블을 업데이트한 다음 변경 내용을 데이터베이스에 복사할 필요 없이, 동적 SQL 명령을 실행하여 레코드를 업데이트하거나 삽입 또는 삭제할 수 있습니다.  
  
-   SUM, COUNT, AVG 등의 집계 함수의 결과와 같은 스칼라 값\(즉, 단일 값\)을 반환하는 명령을 실행할 수 있습니다.  
  
-   SQL Server 데이터베이스\(7.0 이상\)의 데이터를 XML 형식으로 반환하는 명령을 실행할 수 있습니다.  이 방법은 쿼리를 실행하여 XML 형식으로 데이터를 얻고, XSLT 변환을 적용하여 데이터를 HTML 형식으로 변환한 다음 결과를 브라우저로 보낼 때 주로 사용됩니다.  
  
 명령의 속성에는 다음 정보를 포함하여 데이터베이스에 명령을 실행하는 데  이러한 정보는 다음과 같습니다.  
  
-   **연결** 명령에는 데이터베이스와 통신하기 위해 사용하는 연결에 대한 참조가 들어 있습니다.  
  
-   **명령의 이름 또는 텍스트** 명령에는 SQL 문의 실제 텍스트 또는 실행할 저장 프로시저의 이름이 들어 있습니다.  
  
-   **매개 변수** 일부 명령에는 실행할 때 매개 변수 값\(입력 매개 변수\)을 전달해야 합니다.  반환 값 또는 출력 매개 변수 값의 형태로 값을 반환하는 명령도 있습니다.  각 명령에는 개별적으로 전달할 값을 설정하거나 반환되는 값을 읽을 수 있는 매개 변수 컬렉션이 있습니다.  자세한 내용은 [방법: 명령 개체의 매개 변수 설정 및 가져오기](../Topic/How%20to:%20Set%20and%20Get%20Parameters%20for%20Command%20Objects.md)를 참조하십시오.  
  
 얻으려는 결과에 적합한 메서드를 사용하여 명령을 실행합니다.  예를 들어, 행을 얻으려면 데이터 판독기에 레코드를 반환하도록 명령의 `ExecuteReader` 메서드를 호출합니다.  UPDATE, INSERT 또는 DELETE 명령을 수행할 때에는 영향을 받은 행의 개수를 나타내는 값을 반환하도록 명령의 `ExecuteNonQuery` 메서드를 호출합니다.  고객의 주문 수를 반환하는 등의 작업을 하는 집계 함수를 수행하는 경우 `ExecuteScalar` 메서드를 호출합니다.  
  
### 여러 결과 집합  
 명령 개체의 일반적인 용도는 단일 데이터 테이블\(행 집합\)을 반환하는 것입니다.  그러나 여러 개의 결과 집합을 반환하는 프로시저를 명령에서 수행할 수도 있으며  그 방법은 다양합니다.  여러 결과 집합을 반환하는 저장 프로시저를 명령에서 참조하거나,  두 개 이상의 명령문 또는 저장 프로시저 이름을 명령에 포함할 수도 있습니다.  그러면 명령문 또는 프로시저들이 순서대로 실행되어 한 번의 호출에서 여러 결과 집합이 반환됩니다.  
  
 단일 명령에 지정하는 여러 명령문 또는 프로시저는 형식이 모두 같아야 합니다.  예를 들어, 여러 SQL 문을 연이어 실행하거나 여러 저장 프로시저를 연이어 실행할 수는 있지만  단일 명령에서 저장 프로시저 호출과 SQL 문을 혼합할 수는 없습니다.  자세한 내용은 [DataReader를 사용하여 데이터 검색](../Topic/Retrieving%20Data%20Using%20a%20DataReader.md)을 참조하십시오.  
  
> [!NOTE]
>  Oracle의 경우, .NET Framework Data Provider for Oracle에서는 일괄 처리 SQL 문이 지원되지 않습니다.  그러나 .NET Framework Data Provider for Oracle을 사용하면 여러 REF CURSOR 출력 매개 변수를 통해 각각의 데이터 테이블에서 데이터 집합을 채울 수 있습니다.  매개 변수를 정의하고 이 매개 변수를 출력 매개 변수로 표시한 다음 REF CURSOR 데이터 형식으로 지정합니다.  <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 저장 프로시저에 대한 REF CURSOR 매개 변수로 채워진 경우에는 `Update` 메서드를 사용할 수 없습니다. Oracle에서는 SQL 문이 실행될 때 테이블 이름과 열 이름을 결정하는 데 필요한 정보가 제공되지 않기 때문입니다.  
  
## 보안  
 `CommandType` 속성을 <xref:System.Data.CommandType>로 설정한 상태에서 데이터 명령을 사용하는 경우, 클라이언트에서 전송된 정보를 데이터베이스에 전달하기 전에 이 정보를 자세히 검사해야 합니다.  악의적인 사용자가 데이터베이스에 무단으로 액세스하거나 데이터베이스를 훼손하기 위해 수정된 SQL 문이나 추가적인 SQL 문을 전송\(주입\)할 수도 있습니다.  사용자 입력을 데이터베이스에 전송하기 전에 항상 해당 정보의 유효성을 검사해야 합니다.  가능하면 항상 매개 변수가 있는 쿼리나 저장 프로시저를 사용하는 것이 좋습니다.  
  
## 참고 항목  
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [Visual Studio에서 데이터 소스 작업을 위한 도구](../Topic/Tools%20for%20Working%20with%20Data%20Sources%20in%20Visual%20Studio.md)