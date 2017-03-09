---
title: "컴파일러 오류 CS1920 | Microsoft Docs"
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
  - "CS1920"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1920"
ms.assetid: efb4782f-a222-4fb5-9e79-8bd2d380520b
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1920
요소 이니셜라이저는 비워 둘 수 없습니다.  
  
 컬렉션 이니셜라이저는 요소 이니셜라이저의 시퀀스로 구성됩니다. 요소 이니셜라이저는 할당 식을 포함하고 있지 않다면 중괄호로 묶을 필요가 없습니다. 그러나 중괄호를 제공하는 경우 비어 있을 수 없습니다. 요소 이니셜라이저가 개체 이니셜라이저인 경우 이니셜라이저에 새 개체 생성 식이 포함되어 있는 동안 중괄호가 비어 있을 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   누락된 식을 중괄호 사이에 추가합니다.  
  
-   식이 개체 이니셜라이저가 되도록 하려면 중괄호 앞에 새 개체 생성 식을 추가합니다.  
  
## 예제  
 다음 예제에서는 CS1920을 생성합니다.  
  
```  
// cs1920.cs using System.Collections.Generic; public class Test { public static int Main() { // Error. Empty initializer // for inner list. List<List<int>> collection = new List<List<int>>() { { } }; // CS1920 // OK. No initializer for inner list. List<List<int>> collection2 = new List<List<int>>() {  }; // OK. Inner list is initialized // to one List<int> with zero elements. List<List<int>> collection3 = new List<List<int>>() { new List<int> { } }; return 0; } }  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)