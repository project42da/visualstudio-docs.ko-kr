---
title: "방법: TableAdapter를 사용하여 데이터 업데이트 | Microsoft Docs"
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
  - "데이터[Visual Studio], TableAdapter"
  - "데이터[Visual Studio], 업데이트"
  - "데이터 저장"
  - "TableAdapter, 데이터 업데이트"
  - "데이터 업데이트, TableAdapter"
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: TableAdapter를 사용하여 데이터 업데이트
데이터 집합의 데이터를 수정하고 유효성을 검사한 후에는 업데이트된 데이터를 다시 데이터베이스에 보낼 수 있습니다.  수정된 데이터를 데이터베이스로 보내려면 [TableAdapter](../data-tools/tableadapter-overview.md)의 `Update` 메서드를 호출합니다.  어댑터의 `Update` 메서드는 단일 데이터 테이블을 업데이트하고 테이블에 있는 각 데이터 행의 <xref:System.Data.DataRow.RowState%2A>를 기반으로 올바른 명령\(INSERT, UPDATE 또는 DELETE\)을 실행합니다.  데이터를 관련 테이블에 저장할 경우 Visual Studio에서는 데이터베이스에 정의된 외래 키 제약 조건에 따라 올바른 순서로 저장을 수행하도록 돕는 TableAdapterManagers 구성 요소를 제공합니다.  자세한 내용은 [계층적 업데이트 개요](../Topic/Hierarchical%20Update%20Overview.md)를 참조하십시오.  
  
> [!NOTE]
>  데이터 집합의 내용으로 데이터 소스를 업데이트하는 동안 오류가 발생할 수 있으므로 어댑터의 `Update` 메서드를 호출하는 코드는 `try`\/`catch` 블록 안에 넣어야 합니다.  
  
 데이터 소스를 업데이트하는 정확한 절차는 비즈니스 요구 사항에 따라 다르지만 사용자 응용 프로그램에는 다음과 같은 단계가 포함되어야 합니다.  
  
1.  `try`\/`catch` 블록에 포함된, 어댑터의 `Update` 메서드를 호출합니다.  
  
2.  예외가 발생하면 오류를 일으킨 데이터 행을 찾습니다.  자세한 내용은 [방법: 오류가 있는 행 찾기](../Topic/How%20to:%20Locate%20Rows%20that%20Have%20Errors.md)를 참조하십시오.  
  
3.  잘못된 행을 가능하면 프로그래밍 방식으로 수정하고 그렇지 않으면 사용자에게 표시하여 직접 수정하게 하여 데이터 행의 문제를 조정한 다음 업데이트를 다시 시도합니다\(<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>\).  
  
## 데이터를 데이터베이스에 저장  
 TableAdapter의 `Update` 메서드를 호출하여 데이터베이스에 기록할 값이 들어 있는 데이터 테이블의 이름을 전달합니다.  
  
#### TableAdapter를 사용하여 데이터 집합이 있는 데이터베이스를 업데이트하려면  
  
-   어댑터의 `Update` 메서드를 `try`\/`catch` 블록에 포함시킵니다.  다음 예제에서는 `try`\/`catch` 블록 내에서 `NorthwindDataSet`의 `Customers` 테이블 내용으로 업데이트를 시도하는 방법을 보여 줍니다.  
  
     [!code-cs[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]  
  
## TableAdapter를 사용하여 데이터 집합에 있는 두 개의 관련 테이블 업데이트  
 데이터 집합에서 관련 테이블을 업데이트할 때는 참조 무결성 제약 조건을 위반할 위험성을 줄이기 위해 올바른 순서로 업데이트해야 합니다.  명령 실행의 순서도 데이터 집합의 <xref:System.Data.DataRowCollection> 인덱스를 따릅니다.  데이터 무결성 오류가 발생하는 것을 막기 위한 가장 좋은 방법은 다음과 같은 순서로 데이터베이스를 업데이트하는 것입니다.  
  
1.  자식 테이블: 레코드 삭제  
  
2.  부모 테이블: 레코드 삽입, 업데이트 및 삭제  
  
3.  자식 테이블: 레코드 삽입 및 업데이트  
  
    > [!NOTE]
    >  둘 이상의 관련 테이블을 업데이트할 경우 한 트랜잭션 안에 모든 업데이트 논리를 포함해야 합니다.  트랜잭션은 변경 내용을 커밋하기 전에 데이터베이스에 대한 모든 관련 변경 내용이 성공적으로 반영되도록 만드는 프로세스입니다.  자세한 내용은 [트랜잭션 및 동시성](../Topic/Transactions%20and%20Concurrency.md)을 참조하십시오.  
  
#### TableAdapter를 사용하여 두 관련 테이블을 업데이트하려면  
  
1.  서로 다른 레코드가 들어 있는 세 개의 임시 데이터 테이블을 만듭니다.  
  
2.  `try`\/`catch` 블록에서 행의 각 하위 집합에 대해 `Update` 메서드를 호출합니다.  업데이트 오류가 발생하면 이를 분기하여 해결해야 합니다.  
  
3.  데이터베이스에 변경 내용을 커밋합니다.  
  
4.  임시 데이터 테이블을 삭제하여 리소스를 해제합니다.  
  
     다음 예제에서는 관련 테이블이 들어 있는 데이터 집합으로 데이터 소스를 업데이트하는 방법을 보여 줍니다.  
  
     [!code-vb[VbRaddataSaving#27](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_2.vb)]
     [!code-cs[VbRaddataSaving#27](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_2.cs)]  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)