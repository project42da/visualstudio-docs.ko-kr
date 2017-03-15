---
title: "컴파일러 오류 CS1931 | Microsoft Docs"
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
  - "CS1931"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1931"
ms.assetid: c0071c3d-ae11-4073-87df-508150daef68
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1931
범위 변수 'variable'이 'variable'의 이전 선언과 충돌합니다.  
  
 다른 모든 선언과 마찬가지로 범위 변수의 선언도 변수의 선언 영역 내에서 고유한 식별자가 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  범위 변수에 고유한 이름을 지정합니다.  
  
## 예제  
 다음 코드에서는 `x` 식별자가 `Main`의 지역 변수 및 쿼리 식의 범위 변수 둘 다로 사용되기 때문에 CS1931을 생성합니다.  
  
```  
// cs1931.cs class Test { static void Main() { int x = 1; var y = from x in Enumerable.Range(1, 100) // CS1931 select x; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)