---
title: "&#39;By&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc36605"
  - "bc36605"
helpviewer_keywords: 
  - "BC36605"
ms.assetid: d0397b6e-bfc2-400c-92fc-efe82036cfdb
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;By&#39;가 필요합니다.
`Order By` 또는 `Group By` 절이 `By` 키워드 없이 지정되었습니다.  
  
 **오류 ID:** BC36605  
  
### 이 오류를 해결하려면  
  
1.  `Order By` 또는 `Group By` 절에 `By` 키워드를 추가합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim customersByCountry = From cust In customers _  
                             Order By cust.Country, cust.City _  
                             Group By CountryName = cust.Country _  
                             Into RegionalCustomers = Group, Count() _  
                             Order By CountryName  
    ```  
  
## 참고 항목  
 [How to: Sort Query Results](../Topic/How%20to:%20Sort%20Query%20Results%20by%20Using%20LINQ%20\(Visual%20Basic\).md)   
 [Order By Clause](/dotnet/visual-basic/language-reference/queries/order-by-clause)   
 [Group By 절](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)