---
title: "컴파일러 오류 CS1952 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1952"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1952"
ms.assetid: 8c560bf9-df93-40f5-a3d8-c66b31cde08f
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1952
식 트리 람다에는 가변 인수가 있는 메서드를 사용할 수 없습니다.  
  
 지원되지 않는 `__arglist` 키워드는 식 트리로 컴파일되는 람다 식에서 허용되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  `__arglist`를 무시합니다.  
  
## 예제  
 다음 코드는 CS1952를 생성합니다.  
  
```  
// cs1952.cs using System; using System.Linq.Expressions; class Test { public static int M(__arglist) { return 1; } static int Main() { Expression<Func<int, int>> f = x => Test.M(__arglist(x)); // CS1952 return 1; } }  
  
```