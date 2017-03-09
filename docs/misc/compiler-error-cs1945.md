---
title: "컴파일러 오류 CS1945 | Microsoft Docs"
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
  - "CS1945"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1945"
ms.assetid: 787f61b0-4767-451c-8c78-8e456b5057eb
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1945
식 트리에는 무명 메서드 식을 사용할 수 없습니다.  
  
 식 트리는 식만 포함할 수 있습니다. 무명 메서드는 문만 나타낼 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  문을 사용하여 식 트리를 만들지 마세요.  
  
## 예제  
 다음 코드에서는 CS1945를 생성합니다.  
  
```  
// cs1945.cs using System; using System.Linq.Expressions; public delegate void D(); class Test { static void Main() { Expression<Func<int, Func<int, bool>>> tree = (x => delegate(int i) { return true; }); // CS1945 } }  
```  
  
## 참고 항목  
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [문, 식, 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/index)