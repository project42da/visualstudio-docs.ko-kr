---
title: "&#39;Equals&#39;에서 &lt;type1&gt; 형식의 값을 &lt;type2&gt; 형식의 값과 비교할 수 없습니다. | Microsoft Docs"
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
  - "vbc36621"
  - "bc36621"
helpviewer_keywords: 
  - "BC36621"
ms.assetid: bd40bf57-3a12-407a-8622-7e428850c77c
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Equals&#39;에서 &lt;type1&gt; 형식의 값을 &lt;type2&gt; 형식의 값과 비교할 수 없습니다.
`Join` 또는 `Group Join` 절의 `Equals` 연산자가 정의되지 않은 방법으로 하나의 데이터 형식을 다른 데이터 형식과 비교하려 했습니다. 예를 들어 `Boolean` 값을 `Date` 형식에 비교합니다.  
  
 **오류 ID:** BC36621  
  
### 이 오류를 해결하려면  
  
-   `Equals` 연산자의 양쪽에 있는 값을 공통된 데이터 형식으로 변환할 수 있는지 확인합니다. 이 작업을 수행하는 데 대한 몇 가지 옵션은 다음과 같습니다.  
  
    -   `CType` 함수를 사용하여 하나 이상의 값을 특정 형식으로 변환합니다.  
  
    -   <xref:System.Convert> 클래스 또는 변환 메서드를 사용하여 하나 이상의 값을 공통되면서도 변경할 수 없는 형식으로 변환합니다.  
  
    -   `ToString` 메서드를 사용하여 값을 문자열로 변환합니다.  
  
## 참고 항목  
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)   
 [Join Clause](/dotnet/visual-basic/language-reference/queries/join-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)