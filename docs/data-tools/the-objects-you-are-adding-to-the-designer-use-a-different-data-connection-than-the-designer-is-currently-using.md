---
title: "디자이너에 추가하려는 개체가 디자이너에서 현재 사용 중인 데이터 연결이 아닌 다른 데이터 연결을 사용합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 디자이너에 추가하려는 개체가 디자이너에서 현재 사용 중인 데이터 연결이 아닌 다른 데이터 연결을 사용합니다.
디자이너에 추가하려는 개체가 디자이너에서 현재 사용 중인 데이터 연결이 아닌 다른 데이터 연결을 사용합니다.디자이너에서 사용 중인 연결을 바꾸시겠습니까?  
  
 항목을 [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)]\([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]\)에 추가하는 경우 모든 항목은 하나의 공유 데이터 연결을 사용합니다.디자인 화면에는 화면의 모든 개체에 대해 하나의 연결을 사용하는 <xref:System.Data.Linq.DataContext>가 표시됩니다. 디자이너에서 현재 사용하는 데이터 연결과 다른 데이터 연결을 사용하는 디자이너에 개체를 추가하면 이 메시지가 나타납니다.이 오류를 해결하려면 기존 연결 유지를 선택하십시오.이 항목을 선택하면 선택한 개체가 추가되지 않습니다.또는 개체 추가를 선택하고 <xref:System.Data.Linq.DataContext> 연결을 새 연결로 다시 설정하십시오.  
  
> [!NOTE]
>  **예**를 클릭하면 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 모든 엔터티 클래스가 새 연결에 매핑됩니다.  
  
### 기존 연결을 선택한 개체에서 사용하는 연결로 대체하려면  
  
-   **예**를 클릭합니다.  
  
     선택한 개체가 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가되고 DataContext.Connection이 새 연결로 설정됩니다.  
  
### 기존 연결을 계속 사용하고 선택한 개체 추가를 취소하려면  
  
-   **아니요**를 클릭합니다.  
  
     작업이 취소됩니다. DataContext.Connection이 기존 연결로 설정됩니다.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)