---
title: "컴파일러 오류 CS0217 | Microsoft Docs"
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
  - "CS0217"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0217"
ms.assetid: ede61095-6e11-4f4a-8e7d-85e7a3f4fc3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0217
사용자 정의 논리 연산자\('operator'\)를 단락\(short circuit\) 연산자로 사용하려면 연산자의 두 매개 변수와 같은 형식을 반환해야 합니다.  
  
 사용자 정의 형식에 대한 연산자를 정의한 다음 연산자를 단락 연산자로 사용하려면 사용자 정의 연산자에 동일한 형식의 반환 값 및 매개 변수가 있어야 합니다. 단락 연산자에 대한 자세한 내용은 [&& 연산자](/dotnet/csharp/language-reference/operators/conditional-and-operator) 및 [&#124;&#124; 연산자](../Topic/%7C%7C%20Operator%20\(C%23%20Reference\).md)를 참조하세요.  
  
 다음 샘플에서는 CS0217을 생성합니다.  
  
```  
// CS0217.cs using System; public class MyClass { public static bool operator true (MyClass f) { return false; } public static bool operator false (MyClass f) { return false; } public static implicit operator int(MyClass x) { return 0; } public static int operator & (MyClass f1, MyClass f2)   // CS0217 // try the following line instead // public static MyClass operator & (MyClass f1, MyClass f2) { return new MyClass(); } public static void Main() { MyClass f = new MyClass(); int i = f && f; } }  
```  
  
## 참고 항목  
 [오버로드할 수 있는 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators)