---
title: "&#39;In&#39;이 필요합니다. | Microsoft Docs"
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
  - "bc36607"
  - "vbc36607"
helpviewer_keywords: 
  - "BC36607"
ms.assetid: f390bca5-12fe-4fe1-bd86-7f8ab66dfbd8
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;In&#39;이 필요합니다.
`From` 또는 `Aggregate` 절이 `In` 연산자 없이 지정되었습니다.`In` 연산자를 사용하여 쿼리할 컬렉션을 식별합니다.  
  
 **오류 ID:** BC36607  
  
### 이 오류를 해결하려면  
  
1.  `From` 또는 `Aggregate` 절에 `In` 연산자 및 키 필드를 추가합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim names = From pers In people Select pers.FirstName, pers.LastName  
    ```  
  
## 참고 항목  
 [From Clause](/dotnet/visual-basic/language-reference/queries/from-clause)   
 [Aggregate Clause](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)