---
title: "컴파일러 오류 CS1947 | Microsoft Docs"
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
  - "CS1947"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1947"
ms.assetid: e2822fba-a176-4466-9cdc-63c44e22ebcb
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1947
범위 변수 'variable name'은 읽기 전용이므로 이 변수에 값을 할당할 수 없습니다.  
  
 범위 변수는 `foreach` 문에서 반복 변수와 유사합니다. 쿼리 식에서 할당할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  범위 변수에 대한 할당을 제거합니다.  
  
2.  필요한 경우 `let` 절을 사용하여 새 범위 변수를 소개하고 해당 변수를 사용하여 값을 저장합니다.  
  
## 예제  
 다음 코드에서는 CS1947을 생성합니다.  
  
```  
// cs1947.cs using System.Linq; class Test { static void Main() { int[] array = new int[] { 1, 2, 3, 4, 5 }; var x = from i in array let k = i select i = 5; // CS1947 x.ToList(); } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)