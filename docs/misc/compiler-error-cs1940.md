---
title: "컴파일러 오류 CS1940 | Microsoft Docs"
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
  - "CS1940"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1940"
ms.assetid: 546e9bba-725d-4ea9-826f-37ec9d832add
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1940
소스 형식 'type'에 쿼리 패턴이 여러 번 구현되어 있습니다. 'method'에 대한 호출이 모호합니다.  
  
 이 오류는 쿼리 메서드의 여러 구현이 정의되었는데 컴파일러에서 쿼리에 사용하기에 가장 적합한 구현을 구분할 수 없는 경우 발생합니다. 다음 예제에서는 두 버전 모두 하나의 `int`를 입력 매개 변수로 사용하고 `int`를 반환 값으로 사용하기 때문에 `Select`의 두 버전에 동일한 서명이 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  각 메서드에 대해 하나의 구현만 제공합니다.  
  
## 예제  
 다음 코드에서는 CS1940을 생성합니다.  
  
```  
// cs1940.cs using System; //must include explicitly for types defined in 3.5 class Test { public delegate int Dele(int x); int num = 0; public int Select(Func<int, int> d) { return d(this.num); } public int Select(Dele d) // CS1940 { return d(this.num) + 1; } public static void Main() { var q = from x in new Test() select x; } }  
```  
  
## 참고 항목  
 [Standard Query Operators Overview](../Topic/Standard%20Query%20Operators%20Overview.md)