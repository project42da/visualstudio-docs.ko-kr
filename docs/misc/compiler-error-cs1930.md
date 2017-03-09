---
title: "컴파일러 오류 CS1930 | Microsoft Docs"
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
  - "CS1930"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1930"
ms.assetid: d28d2334-825c-4ffc-b9e9-f5d61f44d672
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1930
'name' 범위 변수가 이미 선언되었습니다.  
  
 쿼리 식의 범위 변수는 쿼리 식이 종료될 때까지 범위 내에 있습니다. 따라서 고유 식별자가 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  쿼리 식에 사용된 각 범위 변수에 고유한 이름을 지정합니다.  
  
## 예제  
 다음 예제에서는 `from` 절의 범위 변수와 `let` 절에 사용된 범위 변수에 대해 `num` 식별자가 사용되기 때문에 CS1930을 생성합니다.  
  
```  
// cs1930.cs using System.Linq; class Program { static void Main() { int[] nums = { 0, 1, 2, 3, 4, 5 }; var query = from num in nums let num = 3 // CS1930 select num; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)