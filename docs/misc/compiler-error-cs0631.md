---
title: "컴파일러 오류 CS0631 | Microsoft Docs"
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
  - "CS0631"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0631"
ms.assetid: 5ae06b13-7874-4d0d-b256-7d8b33396156
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0631
이 컨텍스트에서는 ref 및 out을 사용할 수 없습니다.  
  
 [indexer](/dotnet/csharp/programming-guide/indexers/index)에 대한 선언은 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0631을 생성합니다.  
  
```  
// CS0631.cs public class MyClass { public int this[ref int i]   // CS0631 // try the following line instead // public int this[int i] { get { return 0; } } } public class MyClass2 { public static void Main() { } }  
```