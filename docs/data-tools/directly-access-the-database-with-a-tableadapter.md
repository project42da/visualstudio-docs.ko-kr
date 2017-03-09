---
title: "방법: TableAdapter를 사용하여 데이터베이스에 직접 액세스 | Microsoft Docs"
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
  - "데이터[Visual Studio], 저장"
  - "데이터베이스[Visual Basic], TableAdapter를 사용하여 액세스"
  - "데이터 집합[Visual Basic], 프로젝트에 추가"
  - "DBDirect 메서드"
  - "GenerateDbDirectMethods 속성"
  - "데이터 저장"
  - "TableAdapter.Delete 메서드"
  - "TableAdapter.GenerateDBDirectMethods 속성"
  - "TableAdapter.Insert 메서드"
  - "TableAdapter.Update 메서드"
  - "TableAdapter"
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: TableAdapter를 사용하여 데이터베이스에 직접 액세스
`InsertCommand`, `UpdateCommand` 및 `DeleteCommand` 이외에도 데이터베이스에 대해 직접 실행할 수 있는 메서드를 가진 TableAdapter를 만들 수 있습니다.  이러한 메서드\(`TableAdapter.Insert`, `TableAdapter.Update` 및 `TableAdapter.Delete`\)는 직접 호출하여 데이터베이스의 데이터를 조작할 수 있습니다.  
  
 이러한 직접 메서드를 만들지 않으려면 **속성** 창에서 TableAdapter의 `GenerateDbDirectMethods` 속성을 `false`로 설정하십시오.  TableAdapter의 주 쿼리 이외에 TableAdapter에 추가된 쿼리는 모두 독립 실행형 쿼리로, 이러한 DbDirect 메서드를 생성하지 않습니다.  
  
## 데이터베이스에 직접 명령 보내기  
 완료하려는 작업을 수행하는 TableAdapter DbDirect 메서드를 호출합니다.  
  
#### 데이터베이스에 직접 새 레코드를 삽입하려면  
  
-   TableAdapter의 `Insert` 메서드를 호출하고 각 열의 값을 매개 변수로 전달합니다.  다음 프로시저에서는 Northwind 데이터베이스 `Region` 테이블을 예제로 사용합니다.  
  
    > [!NOTE]
    >  사용할 수 있는 인스턴스가 없는 경우 원하는 TableAdapter를 인스턴스화합니다.  
  
     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-cs[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]  
  
#### 데이터베이스에서 직접 레코드를 업데이트하려면  
  
-   TableAdapter의 `Update` 메서드를 호출하고 각 열의 새 값과 원래 값을 매개 변수로 전달합니다.  
  
    > [!NOTE]
    >  사용할 수 있는 인스턴스가 없는 경우 원하는 TableAdapter를 인스턴스화합니다.  
  
     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-cs[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]  
  
#### 데이터베이스에서 직접 레코드를 삭제하려면  
  
-   TableAdapter의 `Delete` 메서드를 호출하고 각 열의 값을 `Delete` 메서드의 매개 변수로 전달합니다.  이 예제에서는 Northwind 데이터베이스의 `Region` 테이블을 사용합니다.  
  
    > [!NOTE]
    >  사용할 수 있는 인스턴스가 없는 경우 원하는 TableAdapter를 인스턴스화합니다.  
  
     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-cs[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]  
  
## 참고 항목  
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [명령 및 매개 변수](../Topic/Commands%20and%20Parameters.md)