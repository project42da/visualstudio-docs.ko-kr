---
title: "방법: 데이터베이스에 새 레코드 삽입 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "데이터베이스, 새 레코드 삽입"
  - "레코드, 삽입"
  - "데이터 저장"
  - "TableAdapter, 새 레코드 삽입"
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 데이터베이스에 새 레코드 삽입
데이터베이스에 새 레코드를 삽입하려면 `TableAdapter.Update` 메서드나 TableAdapter의 DBDirect 메서드\(특히 `TableAdapter.Insert` 메서드\) 중 하나를 사용할 수 있습니다.  자세한 내용은 [TableAdapter 개요](../data-tools/tableadapter-overview.md)를 참조하십시오.  
  
 응용 프로그램에서 TableAdapter를 사용하지 않는 경우 상호 작용할 명령 개체를 사용하여 데이터베이스에 새 레코드를 삽입할 수 있습니다\(예: <xref:System.Data.SqlClient.SqlCommand>\).  
  
 응용 프로그램에서 데이터 집합을 사용하여 데이터를 저장하는 경우 `TableAdapter.Update` 메서드를 사용합니다.  `Update` 메서드는 모든 변경 내용\(업데이트, 삽입 및 삭제\)을 데이터베이스로 보냅니다.  
  
 응용 프로그램에서 개체를 사용하여 데이터를 저장하는 경우 또는 데이터베이스에 새 레코드를 만드는 작업을 세밀하게 제어하려는 경우 `TableAdapter.Insert` 메서드를 사용합니다.  
  
 TableAdapter에 `Insert` 메서드가 없으면 TableAdapter가 저장 프로시저를 사용하도록 구성되어 있거나 해당 `GenerateDBDirectMethods` 속성이 `false`로 설정되어 있는 것입니다.  TableAdapter의 `GenerateDBDirectMethods` 속성을 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 내부에서 `true`로 설정한 다음 데이터 집합을 저장하여 TableAdapter를 다시 생성해 보십시오.  TableAdapter에 여전히 `Insert` 메서드가 없으면 테이블에서 개별 행을 구분하는 충분한 스키마 정보를 제공하지 않게 됩니다\(예: 기본 키가 테이블에 설정되어 있지 않는 경우\).  
  
## TableAdapter를 사용한 새 레코드 삽입  
 TableAdapter는 응용 프로그램의 요구 사항에 따라 데이터베이스에 새 레코드를 삽입할 수 있는 여러 가지 방법을 제공합니다.  
  
 응용 프로그램에서 데이터 집합을 사용하여 데이터를 저장하는 경우 데이터 집합의 원하는 <xref:System.Data.DataTable>에 새 레코드를 간단히 추가한 다음 `TableAdapter.Update` 메서드를 호출합니다.  `TableAdapter.Update` 메서드는 <xref:System.Data.DataTable>의 변경 내용을 가져와서 데이터베이스에 보냅니다\(수정 및 삭제된 레코드 포함\).  
  
#### TableAdapter.Update 메서드를 사용하여 데이터베이스에 새 레코드를 삽입하려면  
  
1.  새 <xref:System.Data.DataRow>를 만들고 <xref:System.Data.DataTable.Rows%2A> 컬렉션에 추가하여 원하는 <xref:System.Data.DataTable>에 새 레코드를 추가합니다.  자세한 내용은 [방법: DataTable에 행 추가](../Topic/How%20to:%20Add%20Rows%20to%20a%20DataTable.md)를 참조하십시오.  
  
2.  <xref:System.Data.DataTable>에 새 행을 추가한 후 `TableAdapter.Update` 메서드를 호출합니다.  전체 <xref:System.Data.DataSet>, 하나의 <xref:System.Data.DataTable>, <xref:System.Data.DataRow>의 배열 또는 단일 <xref:System.Data.DataRow>를 전달하여 업데이트할 데이터 양을 제어할 수 있습니다.  
  
     다음 코드에서는 <xref:System.Data.DataTable>에 새 레코드를 추가한 다음 `TableAdapter.Update` 메서드를 호출하여 새 행을 데이터베이스에 저장하는 방법을 보여 줍니다.  이 예제에서는 Northwind 데이터베이스 `Region` 테이블을 사용합니다.  
  
     [!code-vb[VbRaddataSaving#14](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_1.vb)]
     [!code-cs[VbRaddataSaving#14](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_1.cs)]  
  
 응용 프로그램에서 개체를 사용하여 데이터를 저장하는 경우 `TableAdapter.Insert` 메서드를 사용하여 데이터베이스에 직접 새 행을 만들 수 있습니다.  `Insert` 메서드는 각 열의 개별 값을 매개 변수로 사용합니다.  메서드를 호출하면 전달된 매개 변수 값을 사용하여 새 레코드가 데이터베이스에 삽입됩니다.  
  
 다음 프로시저에서는 Northwind 데이터베이스 `Region` 테이블을 예제로 사용합니다.  
  
#### TableAdapter.Insert 메서드를 사용하여 데이터베이스에 새 레코드를 삽입하려면  
  
-   TableAdapter의 `Insert` 메서드를 호출하고 각 열의 값을 매개 변수로 전달합니다.  
  
    > [!NOTE]
    >  사용할 수 있는 인스턴스가 없는 경우 원하는 TableAdapter를 인스턴스화합니다.  
  
     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_2.vb)]
     [!code-cs[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_2.cs)]  
  
## 명령 개체를 사용한 새 레코드 삽입  
 다음 예제에서는 명령 개체를 사용하여 데이터베이스에 직접 새 레코드를 삽입합니다.  명령 및 저장 프로시저 실행을 위한 명령 개체 사용에 대한 자세한 내용은 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)를 참조하십시오.  
  
 다음 프로시저에서는 Northwind 데이터베이스 `Region` 테이블을 예제로 사용합니다.  
  
#### 명령 개체를 사용하여 데이터베이스에 새 레코드를 삽입하려면  
  
-   새 명령 개체를 만들고 해당 `Connection`, `CommandType` 및 `CommandText` 속성을 설정합니다.  
  
     [!code-vb[VbRaddataSaving#16](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_3.vb)]
     [!code-cs[VbRaddataSaving#16](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_3.cs)]  
  
## .NET Framework 보안  
 연결하려는 데이터베이스에 대한 액세스 권한뿐만 아니라 원하는 테이블에 삽입을 수행할 수 있는 권한이 있어야 합니다.  
  
## 참고 항목  
 [방법: 데이터베이스에서 레코드 삭제](../Topic/How%20to:%20Delete%20Records%20in%20a%20Database.md)   
 [방법: 데이터베이스에서 레코드 업데이트](../data-tools/how-to-update-records-in-a-database.md)   
 [방법: 개체에서 데이터베이스로 데이터 저장](../data-tools/save-data-from-an-object-to-a-database.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [ID 또는 Autonumber 값 검색](../Topic/Retrieving%20Identity%20or%20Autonumber%20Values.md)