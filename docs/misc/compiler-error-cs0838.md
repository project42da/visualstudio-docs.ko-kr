---
title: "컴파일러 오류 CS0838 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0838"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0838"
ms.assetid: 22495e47-3331-42ef-921c-f76ff03ef1f7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0838
식 트리에는 다차원 배열 이니셜라이저를 사용할 수 없습니다.  
  
 식 트리의 다차원 배열은 배열 이니셜라이저를 사용하여 초기화할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  식 트리를 만들기 전에 배열을 만들고 초기화합니다.  
  
## 예제  
 다음 예제에서는 CS0838을 생성합니다.  
  
```  
// cs0838.cs using System; using System.Linq; using System.Linq.Expressions; namespace TestNamespace { class Test { static int Main() { Expression<Func<int[,]>> expr = () => new int[2, 2] { { 1, 2 }, { 3, 4 } }; // CS0838 // try the following 2 lines instead int[,] nums = new int[2, 2] { { 1, 2 }, { 3, 4 } }; Expression<Func<int[,]>> expr2 = () => nums; return 1; } } }  
  
```  
  
## 참고 항목  
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)