---
title: "&lt;property name&gt; 속성은 &lt;association name&gt; 연결에 참여하고 있으므로 삭제할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;property name&gt; 속성은 &lt;association name&gt; 연결에 참여하고 있으므로 삭제할 수 없습니다.
선택한 속성이 오류 메시지에 표시된 클래스 간 연결의 **연결 속성**으로 설정되었습니다.속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 **연결 속성**을 데이터 클래스의 다른 속성으로 설정하면 원하는 속성을 삭제할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  O\/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 연결 선을 선택합니다.  
  
2.  해당 선을 두 번 클릭하여 **연결 편집기** 대화 상자를 엽니다.  
  
3.  **연결 속성**에서 속성을 제거합니다.  
  
4.  속성 삭제를 다시 한 번 시도합니다.  
  
## 참고 항목  
 [O\/R 디자이너 개요](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [방법: LINQ to SQL 클래스 간에 연결 관계 만들기\(O\/R 디자이너\)](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)