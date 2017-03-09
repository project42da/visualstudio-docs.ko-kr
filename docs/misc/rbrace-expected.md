---
title: "&#39;}&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc30370"
  - "bc30370"
helpviewer_keywords: 
  - "BC30370"
ms.assetid: a4ce9be9-fc5d-46ec-a217-c3428bd0b97e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;}&#39;가 필요합니다.
배열 이니셜라이저 또는 제약 조건 목록이 올바른 방식으로 끝나지 않았습니다.  
  
 배열을 초기화할 요소 값을 중괄호\(`{}`\)로 묶어야 합니다.  
  
```  
Dim demoArray() As Integer = New Integer() {1, 2, 3}   
```  
  
 마찬가지로, 제네릭 형식 매개 변수에 대한 제약 조건 목록의 제약 조건도 중괄호로 묶어야 합니다.  
  
```  
Public Class dictionaryMaker(Of t As {IComparable, IDisposable, New})   
```  
  
 **오류 ID:** BC30370  
  
### 이 오류를 해결하려면  
  
-   "}"를 사용하여 배열 이니셜라이저 또는 제약 조건 목록을 끝냅니다.  
  
## 참고 항목  
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)   
 [How to: Initialize an Array Variable in Visual Basic](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)