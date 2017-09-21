---
title: "DataContext 메서드의 반환 형식을 변경하면 실행 취소할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DataContext 메서드의 반환 형식을 변경하면 실행 취소할 수 없습니다.
DataContext 메서드의 반환 형식을 변경하면 실행 취소할 수 없습니다.자동으로 생성된 형식으로 되돌리려면 항목을 서버 탐색기\/데이터베이스 탐색기에서 O\/R 디자이너로 끌어 와야 합니다.반환 형식을 변경하시겠습니까?  
  
 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 항목을 놓는 위치에 따라 달라집니다.항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.항목을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다.<xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 검사하거나 변경하려면 해당 메서드를 선택하고 **속성** 창에서 **반환 형식**을 클릭합니다.  
  
### DataContext의 반환 형식을 변경하려면  
  
-   **예**를 클릭합니다.  
  
### 반환 형식을 변경하지 않고 메시지 상자를 끝내려면  
  
-   **아니요**를 클릭합니다.  
  
### 반환 형식을 변경한 후 원래 반환 형식으로 되돌리려면  
  
1.  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 <xref:System.Data.Linq.DataContext> 메서드를 선택한 다음 삭제합니다.  
  
2.  **서버 탐색기\/데이터베이스 탐색기**에서 항목을 찾아 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 끌어 옵니다.  
  
     원래 기본 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기\(O\/R 디자이너\)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)