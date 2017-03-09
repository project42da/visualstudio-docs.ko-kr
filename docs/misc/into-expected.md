---
title: "&#39;Into&#39;가 필요합니다. | Microsoft Docs"
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
  - "bc36615"
  - "vbc36615"
helpviewer_keywords: 
  - "BC36615"
ms.assetid: 24062dd9-a973-43b6-88d3-c11adc5a3736
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Into&#39;가 필요합니다.
`Aggregate`, `Group By` 또는 `Group Join` 절이 `Into` 연산자 없이 지정되었습니다.`Into` 연산자를 사용하여 쿼리 결과에 적용되는 집계 함수를 식별하고, 쿼리 결과 형식의 멤버를 식별하여 그룹화된 결과를 포함합니다\(`Group` 집계 함수 사용\).  
  
 **오류 ID:** BC36615  
  
### 이 오류를 해결하려면  
  
1.  `Into` 연산자를 `Aggregate`, `Group By` 또는 `Group Join` 절에 추가합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## 참고 항목  
 [Aggregate Clause](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Group By 절](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)