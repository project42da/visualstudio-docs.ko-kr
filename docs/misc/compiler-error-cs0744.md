---
title: "컴파일러 오류 CS0744 | Microsoft Docs"
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
  - "CS0744"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0744"
ms.assetid: 7ce430d6-737a-4103-9116-d9a4a69f8af3
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0744
키워드 'equals'가 필요합니다.  
  
 다음 예제와 같이 `join` 절에 대한 패턴은 `join`...`in`...`on`...`equals`입니다.  
  
```  
var query = from x in array1 join y in array2 on x equals y select x;  
```  
  
### 이 오류를 해결하려면  
  
1.  `join` 절에 `equals` 키워드를 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0744를 생성합니다.  
  
```  
// cs0744.cs using System; using System.Linq; public class C { public static int Main() { int[] array1 = { 1, 2, 3 ,4, 5, 6,}; int[] array2 = { 5, 6, 7, 8, 9 }; var c = from x in array1 join y in array2 on x y // CS0744 select x; return 1; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)   
 [join 절](/dotnet/csharp/language-reference/keywords/join-clause)