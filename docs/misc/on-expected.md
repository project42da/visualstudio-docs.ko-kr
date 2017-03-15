---
title: "&#39;On&#39;이 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36618"
  - "vbc36618"
helpviewer_keywords: 
  - "BC36618"
ms.assetid: 7cb1b205-c4c3-4485-ae3f-8942425692ff
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;On&#39;이 필요합니다.
`Join` 또는 `Group Join` 절이 `On` 연산자 없이 지정되었습니다.`On` 연산자를 사용하여 각 컬렉션에 대한 범위 변수의 키 필드를 식별합니다. 키 필드는 각 컬렉션의 항목을 일치시키는 데 사용됩니다.  
  
 **오류 ID:** BC36618  
  
### 이 오류를 해결하려면  
  
1.  `Join` 또는 `Group Join` 절에 `On` 연산자 및 키 필드를 추가합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim petOwnersJoin = From pers In people _ Join pet In pets _ On pet.Owner Equals pers _ Select pers.FirstName, PetName = pet.Name  
    ```  
  
## 참고 항목  
 [How to: Combine Data with Joins](../Topic/How%20to:%20Combine%20Data%20with%20LINQ%20by%20Using%20Joins%20\(Visual%20Basic\).md)   
 [Join Clause](/dotnet/visual-basic/language-reference/queries/join-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)