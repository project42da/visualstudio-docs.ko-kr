---
title: "&#39;&lt;variablename&gt;&#39;이 포함된 식에서 &#39;&lt;variablename&gt;&#39; 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc30980"
  - "bc30980"
helpviewer_keywords: 
  - "BC30980"
ms.assetid: 43a5d008-5362-481b-845b-b9bb00a61a83
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;variablename&gt;&#39;이 포함된 식에서 &#39;&lt;variablename&gt;&#39; 형식을 유추할 수 없습니다.
선언에서 초기 값을 설정할 때 변수를 사용하는 경우 컴파일러에서 변수의 데이터 형식을 유추할 수 없습니다.  
  
 예를 들어 `Option Infer`가 `On`으로 설정된 경우 다음 예제는 컴파일되지 않습니다.  
  
-   선언  
  
    ```  
    ' Does not compile with Option Infer on. Dim m = m Dim d = someFunction(d)  
    ```  
  
-   `For` 루프  
  
    ```  
    ' Does not compile with Option Infer on. For j = 1 To j Next  
    ```  
  
-   `For Each` 루프  
  
    ```  
    ' Does not compile with Option Infer on. For Each customer In customer.Orders Next  
    ```  
  
 **오류 ID:** BC30980  
  
### 이 오류를 해결하려면  
  
-   두 개의 변수가 서로 다른 값을 참조해야 하는 경우 선언하는 변수의 이름을 변경합니다.  
  
-   할당의 오른쪽에서 초기 값에 변수 이름 대신 리터럴 값을 사용합니다.  
  
-   `As` 절을 사용하여 선언하는 변수의 형식을 지정합니다.  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [For Each...Next 문](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)   
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Local Type Inference](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement)