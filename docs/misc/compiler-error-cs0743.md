---
title: "컴파일러 오류 CS0743 | Microsoft Docs"
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
  - "CS0743"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0743"
ms.assetid: 0dc8040a-a12f-4da6-9ed0-c0284905ee83
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0743
키워드 'on'이 필요합니다.  
  
 다음 예제와 같이 `join` 절에 대한 패턴은 `join`...`in`...`on`...`equals`입니다.  
  
```  
var query = from x in array1 join y in array2 on x equals y select x;  
```  
  
### 이 오류를 해결하려면  
  
1.  `join` 절에 `on` 키워드를 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0743을 생성합니다.  
  
```  
// cs0743.cs using System; using System.Linq; public class C { public static int Main() { int[] array1 = { 1, 2, 3 ,4, 5, 6,}; int[] array2 = { 5, 6, 7, 8, 9 }; var c = from x in array1 join y in array2 x equals y // CS0743 select x; return 1; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)   
 [join 절](/dotnet/csharp/language-reference/keywords/join-clause)