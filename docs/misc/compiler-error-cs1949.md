---
title: "컴파일러 오류 CS1949 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1949"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1949"
ms.assetid: 959f553e-ac3d-43a1-b0a0-11e270f2ad64
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1949
범위 변수 선언에는 상황별 키워드 'var'을 사용할 수 없습니다.  
  
 범위 변수가 컴파일러에 의해 암시적으로 형식화되었습니다. 범위 변수와 함께 [var](/dotnet/csharp/language-reference/keywords/var)을 사용할 필요가 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  범위 변수 앞에서 `var`  키워드를 제거합니다.  
  
## 예제  
 다음 예제에서는 CS1949를 생성합니다.  
  
```  
// cs1949.cs using System; using System.Linq; class Test { static void Main() { var x = from var i in Enumerable.Range(1, 100) // CS1949 select i; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)   
 [Introduction to LINQ Queries \(C\#\)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)