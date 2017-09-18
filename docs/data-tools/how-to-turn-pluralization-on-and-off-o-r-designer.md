---
title: "방법: 복수 적용 설정 및 해제(O/R 디자이너) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 복수 적용 설정 및 해제(O/R 디자이너)
기본적으로 이름이 s 또는 ies로 끝나는 데이터베이스 개체를 **서버 탐색기**\/**데이터베이스 탐색기**에서 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)로 끌면 생성된 엔터티 클래스의 이름이 복수형에서 단수형으로 변경됩니다.이렇게 하면 인스턴스화된 엔터티 클래스를 데이터의 단일 레코드에 매핑하는 것을 보다 정확하게 나타낼 수 있습니다.예를 들어 Customers 테이블을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가하면 단일 고객에 대한 데이터만 해당 클래스에 보유되므로 Customer라는 엔터티 클래스가 만들어집니다.  
  
> [!NOTE]
>  복수 적용은 기본적으로 Visual Studio 영어 버전에만 적용됩니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### 복수 적용을 설정 및 해제하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **데이터베이스 도구**를 확장합니다.  
  
> [!NOTE]
>  **데이터베이스 도구** 노드가 표시되지 않은 경우에는 **모든 설정 표시**를 선택합니다.  
  
1.  **O\/R 디자이너**를 클릭합니다.  
  
2.  **복수 이름 적용**을 **Enabled** \= **False**로 설정하면 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 클래스 이름을 변경하지 못하도록 설정됩니다.  
  
3.  **복수 이름 적용**을 **Enabled** \= **True**로 설정하면 복수 적용 규칙이 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가된 개체의 클래스 이름에 적용됩니다.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)