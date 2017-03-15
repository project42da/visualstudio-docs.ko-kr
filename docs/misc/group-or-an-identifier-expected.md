---
title: "&#39;Group&#39; 또는 식별자가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36707"
  - "bc36707"
helpviewer_keywords: 
  - "BC36707"
ms.assetid: 214e4aa3-d20f-41b3-902c-f1076d31b832
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Group&#39; 또는 식별자가 필요합니다.
`Group By` 또는 `Group Join` 절의 `Into` 부분이 `Group` 키워드를 포함하지 않습니다. 그룹화된 결과에 대해 사용할 변수 이름을 식별하려면 `Group By` 또는 `Group Join` 절의 `Into` 절에 `Group` 키워드를 포함해야 합니다. 이는 지정하는 이름 또는 키워드 `Group`이 될 수 있습니다.  
  
 **오류 ID:** BC36707  
  
### 이 오류를 해결하려면  
  
1.  다음 예제처럼 `Group By` 또는 `Group Join` 절의 `Into` 부분이 `Group` 키워드를 포함하고 있는지 확인합니다.  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Group By 절](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)