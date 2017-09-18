---
title: "방법: LINQ to SQL 클래스 간에 연결 관계 만들기(O/R 디자이너) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: LINQ to SQL 클래스 간에 연결 관계 만들기(O/R 디자이너)
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]에서 엔터티 클래스 간의 연결은 데이터베이스 테이블 간의 관계와 비슷합니다.**연결 편집기** 대화 상자를 사용하여 엔터티 클래스 간의 연결을 만들 수 있습니다.  
  
 **연결 편집기** 대화 상자에서 연결을 만들 때 부모 클래스와 자식 클래스를 선택해야 합니다.부모 클래스는 기본 키가 있는 엔터티 클래스이고, 자식 클래스는 외래 키가 있는 엔터티 클래스입니다.예를 들어 Northwind Customers 및 Orders 테이블에 매핑되는 엔터티 클래스를 만들면 Customer 클래스는 부모 클래스가 되고 Order 클래스는 자식 클래스가 됩니다.  
  
> [!NOTE]
>  **서버 탐색기**\/**데이터베이스 탐색기**에서 [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)]\([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]\)로 테이블을 끌어 오면 데이터베이스의 기존 외래 키 관계를 기준으로 연결이 자동으로 만들어집니다.  
  
 연결을 만든 후 O\/R 디자이너에서 연결을 선택하면 **속성** 창에 몇 개의 구성 가능한 속성이 나타납니다.연결은 관련 클래스 간의 선입니다. 다음 표에서는 연결 속성을 설명합니다.  
  
|속성|설명|  
|--------|--------|  
|**카디널리티**|연결이 일대다 연결인지 또는 일대일 연결인지를 제어합니다.|  
|**자식 속성**|연결의 외래 키 쪽에서 자식 레코드의 컬렉션이거나 자식 레코드에 대한 참조인 부모 속성을 만들지 여부를 지정합니다.예를 들어 Customer와 Order 간의 연결에서 **자식 속성**을 **True**로 설정하면 Orders라는 속성이 부모 클래스에 만들어집니다.|  
|**부모 속성**|연결된 부모 클래스를 참조하는 자식 클래스의 속성입니다.예를 들어 Customer와 Order 간의 연결에서 연결된 주문 고객을 참조하는 Customer라는 속성이 Order 클래스에 만들어집니다.|  
|**참여 속성**|연결 속성을 표시하고 **연결 편집기** 대화 상자를 다시 여는 **줄임표** 단추\(...\)를 제공합니다.|  
|**고유**|외래 대상 열에 고유성 제약 조건이 있는지 여부를 지정합니다.|  
  
### 엔터티 클래스 간에 연결을 만들려면  
  
1.  연결에서 부모 클래스를 나타내는 엔터티 클래스를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **연결**을 클릭합니다.  
  
2.  **연결 편집기** 대화 상자에서 올바른 **부모 클래스**가 선택되었는지 확인합니다.  
  
3.  콤보 상자에서 **자식 클래스**를 선택합니다.  
  
4.  클래스가 관련된 **연결 속성**을 선택합니다.일반적으로 이는 데이터베이스에 정의된 외래 키 관계에 매핑됩니다.예를 들어 Customers 및 Orders 연결에서 **연결 속성**은 각 클래스의 CustomerID입니다.  
  
5.  **확인**을 클릭하여 연결을 만듭니다.  
  
## 참고 항목  
 [O\/R 디자이너 개요](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 기본 키 나타내기](../Topic/How%20to:%20Represent%20Primary%20Keys.md)