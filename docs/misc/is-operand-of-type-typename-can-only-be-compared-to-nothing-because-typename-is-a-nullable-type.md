---
title: "&#39;typename&#39;이 nullable 형식이므로 &#39;typename&#39; 형식의 &#39;Is&#39; 피연산자는 &#39;Nothing&#39;하고만 비교할 수 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32127"
  - "bc32127"
helpviewer_keywords: 
  - "BC32127"
ms.assetid: 68b745b5-8605-4bf3-a6ec-69e67b3cff2d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;typename&#39;이 nullable 형식이므로 &#39;typename&#39; 형식의 &#39;Is&#39; 피연산자는 &#39;Nothing&#39;하고만 비교할 수 있습니다.
nullable로 선언된 변수가 `Is` 연산자를 사용하여 `Nothing` 이외의 식과 비교되었습니다.  
  
 **오류 ID:** BC32127  
  
### 이 오류를 해결하려면  
  
1.  `Is` 연산자를 사용하여 nullable 형식을 `Nothing` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.  
  
    ```vb#  
    Dim number? As Integer = 5 If number IsNot Nothing Then If number.GetType() Is Type.GetType("System.Int32") Then End If End If  
    ```  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)   
 [Is Operator](/dotnet/visual-basic/language-reference/operators/is-operator)