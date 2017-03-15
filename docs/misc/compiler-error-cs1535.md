---
title: "컴파일러 오류 CS1535 | Microsoft Docs"
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
  - "CS1535"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1535"
ms.assetid: 19f41e78-9aea-4575-abd0-60ddb927276f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1535
오버로드된 'operator' 단항 연산자는 매개 변수를 한 개 사용합니다.  
  
 단항 [오버로드할 수 있는 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators)의 정의는 두 개의 매개 변수를 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS1535를 생성합니다.  
  
```  
// CS1535.cs class MyClass { // uncomment the method parameter to resolve CS1535 public static MyClass operator ++ (/*MyClass MC1*/)   // CS1535 { return new MyClass(); } public static int Main() { return 1; } }  
```