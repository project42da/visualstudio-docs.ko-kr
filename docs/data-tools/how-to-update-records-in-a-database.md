---
title: "방법: 데이터베이스에서 레코드 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
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
  - "데이터[Visual Studio], 저장"
  - "데이터베이스, 업데이트"
  - "레코드, 편집"
  - "레코드, 업데이트"
  - "TableAdapter.Update 메서드"
ms.assetid: cdc8a8e4-a5fa-40dd-9221-97b8571d802a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 데이터베이스에서 레코드 업데이트
`TableAdapter.Update` 메서드를 사용하여 데이터베이스의 레코드를 업데이트\(편집\)할 수 있습니다.  `TableAdapter.Update` 메서드는 전달된 매개 변수에 따라 다른 작업을 수행하는 여러 개의 오버로드를 제공합니다.  이러한 여러 메서드 시그니처의 호출 결과를 이해하는 것이 중요합니다.  
  
> [!NOTE]
>  응용 프로그램에서 TableAdapter를 사용하지 않는 경우 명령 개체를 사용하여 데이터베이스의 레코드를 업데이트할 수 있습니다\(예: <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>\).  명령 개체를 사용한 데이터 업데이트에 대한 자세한 내용은 아래 "명령 개체를 사용하여 레코드 업데이트"를 참조하십시오.  
  
 다음 표에서는 여러 `TableAdapter.Update` 메서드의 동작에 대해 설명합니다.  
  
|메서드|설명|  
|---------|--------|  
|`TableAdapter.Update(DataTable)`|<xref:System.Data.DataTable>의 모든 변경 내용을 데이터베이스에 저장하려고 시도합니다.  여기에는 테이블에서 삭제된 행 제거, 테이블에 삽입된 행 추가 및 테이블에서 변경된 행 업데이트가 포함됩니다.|  
|`TableAdapter.Update(DataSet)`|매개 변수가 데이터 집합을 사용하지만 TableAdapter는 TableAdapter의 연결된 <xref:System.Data.DataTable>에 있는 모든 변경 내용을 데이터베이스에 저장하려고 시도합니다.  여기에는 테이블에서 삭제된 행 제거, 테이블에 삽입된 행 추가 및 테이블에서 변경된 행 업데이트가 포함됩니다. **Note:**  TableAdapter의 연결된 <xref:System.Data.DataTable>은 TableAdapter가 원래 구성될 때 만들어진 <xref:System.Data.DataTable>입니다.|  
|`TableAdapter.Update(DataRow)`|표시된 <xref:System.Data.DataRow>의 변경 내용을 데이터베이스에 저장하려고 시도합니다.|  
|`TableAdapter.Update(DataRows())`|<xref:System.Data.DataRow>의 배열에서 모든 행의 변경 내용을 데이터베이스에 저장하려고 시도합니다.|  
|`TableAdapter.Update("new column values", "original column values")`|원래 열 값으로 식별되는 단일 행의 변경 내용을 저장하려고 시도합니다.|  
  
 응용 프로그램에서 데이터 집합만 사용하여 데이터를 저장하는 경우 일반적으로 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow>를 사용하는 `TableAdapter.Update` 메서드를 사용합니다.  
  
 응용 프로그램에서 개체를 사용하여 데이터를 저장하는 경우 일반적으로 열 값을 사용하는 `TableAdapter.Update` 메서드를 사용합니다.  
  
 TableAdapter에 열 값을 사용하는 `Update` 메서드가 없으면 TableAdapter가 저장 프로시저를 사용하도록 구성되어 있거나 해당 `GenerateDBDirectMethods` 속성이 `false`로 설정되어 있는 것입니다.  TableAdapter의 `GenerateDBDirectMethods` 속성을 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 내부에서 `true`로 설정한 다음 데이터 집합을 저장하여 TableAdapter를 다시 생성해 보십시오.  TableAdapter에 여전히 열 값을 사용하는 `Update` 메서드가 없으면 테이블에서 개별 행을 구분하는 충분한 스키마 정보를 제공하지 않게 됩니다\(예: 기본 키가 테이블에 설정되어 있지 않는 경우\).  
  
## TableAdapter를 사용하여 기존 레코드 업데이트  
 TableAdapter는 응용 프로그램의 요구 사항에 따라 데이터베이스에서 레코드를 업데이트할 수 있는 여러 가지 방법을 제공합니다.  
  
 응용 프로그램에서 데이터 집합을 사용하여 데이터를 저장하는 경우 원하는 <xref:System.Data.DataTable>에서 레코드를 간단히 업데이트한 다음 `TableAdapter.Update` 메서드를 호출하고 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow> 또는 <xref:System.Data.DataRow>의 배열을 전달할 수 있습니다.  위의 표에서는 여러 `Update` 메서드에 대해 설명합니다.  
  
#### DataSet, DataTable, DataRow 또는 DataRows\(\)를 사용하는 TableAdapter.Update 메서드로 데이터베이스의 레코드를 업데이트하려면  
  
1.  <xref:System.Data.DataTable>의 <xref:System.Data.DataRow>를 직접 편집하여 원하는 <xref:System.Data.DataTable>의 레코드를 편집합니다.  자세한 내용은 [방법: DataTable의 행 편집](../Topic/How%20to:%20Edit%20Rows%20in%20a%20DataTable.md)을 참조하십시오.  
  
2.  <xref:System.Data.DataTable>에서 행을 편집한 후 `TableAdapter.Update` 메서드를 호출합니다.  전체 <xref:System.Data.DataSet>, 하나의 <xref:System.Data.DataTable>, <xref:System.Data.DataRow>의 배열 또는 단일 <xref:System.Data.DataRow>를 전달하여 업데이트할 데이터 양을 제어할 수 있습니다.  
  
     다음 코드에서는 <xref:System.Data.DataTable>에서 레코드를 편집한 다음 `TableAdapter.Update` 메서드를 호출하여 변경 내용을 데이터베이스에 저장하는 방법을 보여 줍니다.  이 예제에서는 Northwind 데이터베이스 Region 테이블을 사용합니다.  
  
     [!code-vb[VbRaddataSaving#17](../data-tools/codesnippet/VisualBasic/how-to-update-records-in-a-database_1.vb)]
     [!code-cs[VbRaddataSaving#17](../data-tools/codesnippet/CSharp/how-to-update-records-in-a-database_1.cs)]  
  
 응용 프로그램에서 개체를 사용하여 데이터를 저장하는 경우 TableAdapter의 `DBDirect` 메서드를 사용하여 개체에서 데이터베이스로 직접 데이터를 보낼 수 있습니다.  이러한 메서드를 사용하면 각 열의 개별 값을 메서드 매개 변수로 전달할 수 있습니다.  이 메서드를 호출하면 메서드에 전달된 열 값을 사용하여 데이터베이스의 기존 레코드가 업데이트됩니다.  
  
 다음 프로시저에서는 Northwind `Region` 테이블을 예제로 사용합니다.  
  
#### 열 값을 사용하는 TableAdapter.Update 메서드를 사용하여 데이터베이스의 레코드를 업데이트하려면  
  
-   TableAdapter의 `Update` 메서드를 호출하고 각 열의 새 값과 원래 값을 매개 변수로 전달합니다.  
  
    > [!NOTE]
    >  사용할 수 있는 인스턴스가 없는 경우 원하는 TableAdapter를 인스턴스화합니다.  
  
     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/how-to-update-records-in-a-database_2.vb)]
     [!code-cs[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/how-to-update-records-in-a-database_2.cs)]  
  
## 명령 개체를 사용하여 레코드 업데이트  
 다음 예제에서는 명령 개체를 사용하여 데이터베이스에서 직접 기존 레코드를 업데이트합니다.  명령 및 저장 프로시저 실행을 위한 명령 개체 사용에 대한 자세한 내용은 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)를 참조하십시오.  
  
 다음 프로시저에서는 Northwind `Region` 테이블을 예제로 사용합니다.  
  
#### 명령 개체를 사용하여 데이터베이스의 기존 레코드를 업데이트하려면  
  
-   새 명령 개체를 만들고 해당 `Connection`, `CommandType` 및 `CommandText` 속성을 설정한 다음 연결을 열고 명령을 실행합니다.  
  
     [!code-vb[VbRaddataSaving#19](../data-tools/codesnippet/VisualBasic/how-to-update-records-in-a-database_3.vb)]
     [!code-cs[VbRaddataSaving#19](../data-tools/codesnippet/CSharp/how-to-update-records-in-a-database_3.cs)]  
  
## .NET Framework 보안  
 연결하려는 데이터베이스에 대한 액세스 권한뿐만 아니라 원하는 테이블에서 레코드를 업데이트할 수 있는 권한이 있어야 합니다.  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: 데이터베이스에서 레코드 삭제](../Topic/How%20to:%20Delete%20Records%20in%20a%20Database.md)   
 [방법: 데이터베이스에 새 레코드 삽입](../data-tools/insert-new-records-into-a-database.md)   
 [방법: 개체에서 데이터베이스로 데이터 저장](../data-tools/save-data-from-an-object-to-a-database.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)