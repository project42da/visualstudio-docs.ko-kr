---
title: "&lt;property name&gt; 속성을 삭제할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# &lt;property name&gt; 속성을 삭제할 수 없습니다.
\<property name\> 속성은 \<class name\>과\(와\) \<class name\> 간 상속의 판별자 속성으로 설정되어 있으므로 삭제할 수 없습니다.  
  
 선택한 속성이 오류 메시지에 표시된 클래스 간 상속의 **판별자 속성**으로 설정되었습니다.속성이 데이터 클래스 간 상속 구성에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 **판별자 속성**을 데이터 클래스의 다른 속성으로 설정하면 원하는 속성을 삭제할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  O\/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 상속 선을 선택합니다.  
  
2.  **판별자** 속성을 다른 속성으로 설정합니다.  
  
3.  속성 삭제를 다시 한 번 시도합니다.  
  
## 참고 항목  
 [방법: O\/R 디자이너를 사용하여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)   
 [데이터 클래스 상속\(O\/R 디자이너\)](../data-tools/data-class-inheritance-o-r-designer.md)   
 [연습: 단일 테이블 상속을 사용하여 LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)