---
title: "데이터베이스에 새 레코드를 삽입 합니다. | Microsoft Docs"
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
- TableAdapters, inserting new records into
- data [Visual Studio], saving
- databases, inserting new records into
- records, inserting
- saving data
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 2450ed950227b6755b57f20f3520a1e75034aafe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="insert-new-records-into-a-database"></a>데이터베이스에 새 레코드를 삽입 합니다.
데이터베이스에 새 레코드를 삽입 하려면 사용할 수 있습니다는 `TableAdapter.Update` 메서드 또는 TableAdapter의 DBDirect 메서드 중 하나 (특히 여 `TableAdapter.Insert` 메서드). 자세한 내용은 참조 [TableAdapter](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
 응용 프로그램에서 Tableadapter를 사용 하지 않는 명령 개체를 사용할 수 있습니다 (예를 들어 <xref:System.Data.SqlClient.SqlCommand>) 데이터베이스에서 새 레코드를 삽입 합니다.
  
 응용 프로그램 데이터 집합을 사용 하 여 데이터를 저장할를 사용 하 여는 `TableAdapter.Update` 메서드. `Update` 메서드는 데이터베이스에 모든 변경 내용 (업데이트, 삽입 및 삭제)를 보냅니다.  
  
 응용 프로그램 개체를 사용 하 여 데이터를 저장 하거나 데이터베이스에 새 레코드를 만드는 보다 세부적으로 제어 하려는 경우 사용 하는 경우는 `TableAdapter.Insert` 메서드.  
  
 프로그램 TableAdapter에 없는 경우는 `Insert` 메서드를 의미 하거나 TableAdapter 저장된 프로시저를 사용 하도록 구성 되어 있는지 또는 해당 `GenerateDBDirectMethods` 속성이 `false`합니다. TableAdapter의 설정 해 보고 `GenerateDBDirectMethods` 속성을 `true` 내에서 **데이터 집합 디자이너**, 데이터 집합을 저장 합니다. 이 TableAdapter 다시 생성 됩니다. TableAdapter 아직 없는 경우는 `Insert` 메서드를 다음 표에 제공 하지 않게 개별 행을 구분 하기 위해 충분 한 스키마 정보 (예를 들어 있을 수 있습니다는 테이블에 기본 키 집합 없음).  
  
## <a name="insert-new-records-by-using-tableadapters"></a>Tableadapter를 사용 하 여 새 레코드를 삽입 합니다.  
 Tableadapter에는 응용 프로그램의 요구 사항에 따라 데이터베이스에 새 레코드를 삽입 하 여 여러 가지 방법을 제공 합니다.  
  
 응용 프로그램 데이터 집합을 사용 하 여 데이터를 저장할 경우를 원하는 새 레코드를 추가 하기만 하면 <xref:System.Data.DataTable> 집합과 호출에는 `TableAdapter.Update` 메서드. `TableAdapter.Update` 메서드 변경 내용을 보냅니다는 <xref:System.Data.DataTable> (수정 및 삭제 된 레코드를 포함 하 여) 데이터베이스에 있습니다.  
  
#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterupdate-method"></a>TableAdapter.Update 메서드를 사용 하 여 데이터베이스에 새 레코드를 삽입 하려면  
  
1.  새 레코드를 원하는 추가 <xref:System.Data.DataTable> 새 <xref:System.Data.DataRow> 추가 하는 <xref:System.Data.DataTable.Rows%2A> 컬렉션입니다. 
  
2.  새 행에 추가 된 후의 <xref:System.Data.DataTable>, 호출 된 `TableAdapter.Update` 메서드. 전체에서 전달 하 여 업데이트 하는 데이터의 양을 제어할 수 있습니다 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 배열을 <xref:System.Data.DataRow>s, 또는 단일 <xref:System.Data.DataRow>합니다.  
  
 다음 코드에서는 새 레코드를 추가 하는 방법을 보여 줍니다.는 <xref:System.Data.DataTable> 다음 호출에서 `TableAdapter.Update` 메서드를 데이터베이스에 새 행을 저장 합니다. (사용 하 여이 예제는 `Region` Northwind 데이터베이스의 테이블입니다.)  
  
 [!code-vb[VbRaddataSaving#14](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_1.vb)]
 [!code-csharp[VbRaddataSaving#14](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_1.cs)]  
  
#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterinsert-method"></a>TableAdapter.Insert 메서드를 사용 하 여 데이터베이스에 새 레코드를 삽입 하려면  
개체를 사용 하 여 데이터를 저장 하는 응용 프로그램을 사용할 수 있습니다는 `TableAdapter.Insert` 메서드는 데이터베이스에 직접 새 행을 만들 수 있습니다. `Insert` 메서드 매개 변수로 각 열에 대 한 개별 값을 사용할 수 있습니다. 데이터베이스에 전달 된 매개 변수 값으로 새 레코드를 삽입 메서드를 호출 합니다.  
  
- TableAdapter의 호출 `Insert` 메서드를 매개 변수로 각 열에 대 한 값에 전달 합니다.  

 다음 절차를 사용 하 여 보여 줍니다.는 `TableAdapter.Insert` 메서드 행을 삽입 합니다. 데이터를 삽입 하는이 예제는 `Region` Northwind 데이터베이스의 테이블입니다.  
  
 > [!NOTE]
 >  인스턴스를 사용할 수 없는 경우 사용 하려는 TableAdapter를 인스턴스화하십시오.  
  
 [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_2.vb)]
 [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_2.cs)]  
  
## <a name="insert-new-records-by-using-command-objects"></a>명령 개체를 사용 하 여 새 레코드를 삽입 합니다.  
명령 개체를 사용 하는 데이터베이스에 직접 새 레코드를 삽입할 수 있습니다.    
  
#### <a name="to-insert-new-records-into-a-database-by-using-command-objects"></a>명령 개체를 사용 하 여 데이터베이스에 새 레코드를 삽입 하려면  
  
-   새 명령 개체를 만들고 다음 설정의 `Connection`, `CommandType`, 및 `CommandText` 속성입니다.  

 다음 예제에서는 명령 개체를 사용 하 여 데이터베이스에 레코드 삽입을 보여 줍니다. 데이터를 삽입 하는 것은 `Region` Northwind 데이터베이스의 테이블입니다.
  
 [!code-vb[VbRaddataSaving#16](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_3.vb)]
 [!code-csharp[VbRaddataSaving#16](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_3.cs)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 원하는 테이블에 삽입을 수행할 수 있는 권한을 뿐만 아니라, 연결 하려는 데이터베이스에 액세스할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)