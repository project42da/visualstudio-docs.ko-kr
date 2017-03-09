---
title: "컴파일러 오류 CS1534 | Microsoft Docs"
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
  - "CS1534"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1534"
ms.assetid: afb28c3a-a74c-4e47-b016-9e3245a5a1b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1534
오버로드된 'operator' 이항 연산자는 매개 변수를 두 개 사용합니다.  
  
 이진 [오버로드할 수 있는 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators)의 정의는 두 개의 매개 변수를 사용해야 합니다.  
  
 다음 샘플에서는 CS1534를 생성합니다.  
  
```  
// CS1534.cs class MyClass { public static MyClass operator - (MyClass MC1, MyClass MC2, MyClass MC3)   // CS1534 // try the following line instead // public static MyClass operator - (MyClass MC1, MyClass MC2) { return new MyClass(); } public static int Main() { return 1; } }  
```