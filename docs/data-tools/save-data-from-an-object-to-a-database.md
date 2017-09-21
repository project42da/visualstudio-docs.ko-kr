---
title: "방법: 개체에서 데이터베이스로 데이터 저장 | Microsoft Docs"
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
  - "데이터 액세스[Visual Studio], 개체"
  - "데이터 저장"
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
caps.latest.revision: 9
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 개체에서 데이터베이스로 데이터 저장
개체에서 TableAdapter의 DBDirect 메서드\(예: `TableAdapter.Insert`\) 중 하나로 값을 전달하여 개체의 데이터를 데이터베이스에 저장할 수 있습니다.  자세한 내용은 [TableAdapter 개요](../data-tools/tableadapter-overview.md)를 참조하십시오.  
  
 개체 컬렉션의 데이터를 저장하려면 개체 컬렉션을 순환 검색하고\(예: for\-next 루프\) TableAdapter의 DBDirect 메서드 중 하나를 사용하여 각 개체의 값을 데이터베이스로 보냅니다.  
  
 기본적으로 DBDirect 메서드는 데이터베이스에 대해 직접 실행할 수 있는 TableAdapter에서 만들어집니다.  이러한 메서드는 직접 호출될 수 있으며 업데이트를 데이터베이스로 보내기 위해 변경 내용을 조정하는 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable> 개체를 필요로 하지 않습니다.  
  
> [!NOTE]
>  TableAdapter를 구성할 때 주 쿼리에서는 DBDirect 메서드를 만들 수 있는 충분한 정보를 제공해야 합니다.  예를 들어, TableAdapter가 정의된 기본 키 열이 없는 테이블의 데이터를 쿼리하도록 구성되어 있는 경우 DBDirect 메서드는 생성되지 않습니다.  
  
|TableAdapter DBDirect 메서드|설명|  
|-------------------------------|--------|  
|`TableAdapter.Insert`|데이터베이스에 새 레코드를 추가하여 개별 열 값을 메서드 매개 변수로 전달할 수 있습니다.|  
|`TableAdapter.Update`|데이터베이스의 기존 레코드를 업데이트합니다.  `Update` 메서드는 원래 열 값과 새 열 값을 메서드 매개 변수로 사용합니다.  원래 값은 원래 레코드를 찾는 데 사용되고 새 값은 해당 레코드를 업데이트하는 데 사용됩니다.<br /><br /> 또한 `TableAdapter.Update` 메서드를 사용하면 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow> 또는 <xref:System.Data.DataRow>의 배열을 메서드 매개 변수로 사용하여 데이터 집합의 변경 내용을 다시 데이터베이스에 적용할 수도 있습니다.|  
|`TableAdapter.Delete`|매서드 매개 변수로 전달된 원래 열 값을 기반으로 데이터베이스에서 기존 레코드를 삭제합니다.|  
  
### 개체의 새 레코드를 데이터베이스에 저장하려면  
  
-   값을 `TableAdapter.Insert` 메서드에 전달하여 레코드를 만듭니다.  
  
     다음 예제에서는 `currentCustomer` 개체의 값을 `TableAdapter.Insert` 메서드에 전달하여 `Customers` 테이블에 새 고객 레코드를 만듭니다.  
  
     [!code-cs[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_1.cs)]
     [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_1.vb)]  
  
### 개체의 기존 레코드를 데이터베이스로 업데이트하려면  
  
-   `TableAdapter.Update` 메서드를 호출하고 레코드를 업데이트할 새 값과 해당 레코드를 찾을 원래 값을 전달하여 레코드를 수정합니다.  
  
    > [!NOTE]
    >  개체는 `Update` 메서드에 전달할 수 있도록 원래 값을 유지해야 합니다.  이 예제에서는 `orig` 접두사가 있는 속성을 사용하여 원래 값을 저장합니다.  
  
     다음 예제에서는 `Customer` 개체의 새 값과 원래 값을 `TableAdapter.Update` 메서드에 전달하여 `Customers` 테이블의 기존 레코드를 업데이트합니다.  
  
     [!code-cs[VbRaddataSaving#24](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_2.cs)]
     [!code-vb[VbRaddataSaving#24](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_2.vb)]  
  
### 데이터베이스에서 기존 레코드를 삭제하려면  
  
-   `TableAdapter.Delete` 메서드를 호출하고 레코드를 찾을 원래 값을 전달하여 해당 레코드를 삭제합니다.  
  
    > [!NOTE]
    >  개체는 `Delete` 메서드에 전달할 수 있도록 원래 값을 유지해야 합니다.  이 예제에서는 `orig` 접두사가 있는 속성을 사용하여 원래 값을 저장합니다.  
  
     다음 예제에서는 `Customer` 개체의 원래 값을 `TableAdapter.Delete` 메서드에 전달하여 `Customers` 테이블에서 레코드를 삭제합니다.  
  
     [!code-cs[VbRaddataSaving#25](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_3.cs)]
     [!code-vb[VbRaddataSaving#25](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_3.vb)]  
  
## .NET Framework 보안  
 데이터베이스의 테이블에서 선택한 INSERT, UPDATE 또는 DELETE 작업을 수행할 수 있는 권한이 있어야 합니다.  
  
## 참고 항목  
 [Visual Studio에서 개체 바인딩](../data-tools/bind-objects-in-visual-studio.md)   
 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)   
 [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)   
 [방법: TableAdapter를 사용하여 데이터베이스에 직접 액세스](../data-tools/directly-access-the-database-with-a-tableadapter.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)