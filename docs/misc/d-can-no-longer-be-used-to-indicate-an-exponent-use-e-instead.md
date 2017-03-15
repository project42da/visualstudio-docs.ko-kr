---
title: "지수를 가리키는 데 더 이상 &#39;D&#39;를 사용할 수 없습니다. 대신 &#39;E&#39;를 사용하세요. | Microsoft Docs"
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
  - "vbc30827"
  - "bc30827"
helpviewer_keywords: 
  - "BC30827"
ms.assetid: 577f8c0b-9e8a-433f-b504-9ddaa936c250
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 지수를 가리키는 데 더 이상 &#39;D&#39;를 사용할 수 없습니다. 대신 &#39;E&#39;를 사용하세요.
'D' 문자는 지수를 나타내는 데 사용할 수 없습니다.  
  
 **오류 ID:** BC30827  
  
### 이 오류를 해결하려면  
  
-   `^` 연산자 또는 `E+` 문자를 사용하여 지수가 있다는 것을 나타냅니다. 예:  
  
    ```  
    Const Mole = 6.02E+23 ' Same as 6.02D23 Const Mole2 = 6.02 * 10 ^ 23 ' Same as 6.02D23  
    ```  
  
## 참고 항목  
 [^ Operator](/dotnet/visual-basic/language-reference/operators/exponentiation-operator)   
 [Numeric Data Types](/dotnet/visual-basic/programming-guide/language-features/data-types/numeric-data-types)