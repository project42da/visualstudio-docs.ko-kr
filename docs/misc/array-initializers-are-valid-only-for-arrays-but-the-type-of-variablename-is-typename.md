---
title: "배열 이니셜라이저는 배열에만 유효하지만 &#39;&lt;variablename&gt;&#39;의 형식은 &#39;&lt;typename&gt;&#39;입니다. | Microsoft Docs"
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
  - "bc30679"
  - "vbc30679"
helpviewer_keywords: 
  - "BC30679"
ms.assetid: 3cf34882-7a58-4074-8ebb-52e58199a506
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열 이니셜라이저는 배열에만 유효하지만 &#39;&lt;variablename&gt;&#39;의 형식은 &#39;&lt;typename&gt;&#39;입니다.
값 목록을 사용하여 배열이 아닌 변수를 초기화하려고 했습니다.  
  
 **오류 ID:** BC30679  
  
### 이 오류를 해결하려면  
  
-   변수를 배열로 선언하고 초기화합니다. 예를 들면 다음과 같습니다.  
  
     `Dim intarray As Integer() = {1, 5, 9}`  
  
-   변수를 단일 값으로 초기화합니다. 예를 들면 다음과 같습니다.  
  
     `Dim intvalue As Integer = 1`  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [변수 선언](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)   
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)