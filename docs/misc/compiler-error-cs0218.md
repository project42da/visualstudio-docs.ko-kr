---
title: "컴파일러 오류 CS0218 | Microsoft Docs"
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
  - "CS0218"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0218"
ms.assetid: f675e06a-c55c-44a1-b5db-0df178fd8f79
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0218
'type' 형식에는 true 및 false 연산자 선언이 있어야 합니다.  
  
 사용자 정의 형식에 대해 연산자를 정의한 다음 연산자를 단락 연산자로 사용하려는 경우 사용자 정의 연산자에 true 연산자 및 false 연산자가 정의되어 있어야 합니다. 단락 연산자에 대한 자세한 내용은 [&& 연산자](/dotnet/csharp/language-reference/operators/conditional-and-operator) 및 [&#124;&#124; 연산자](../Topic/%7C%7C%20Operator%20\(C%23%20Reference\).md)를 참조하세요.  
  
 다음 샘플에서는 CS0218을 생성합니다.  
  
```  
// CS0218.cs using System; public class MyClass { // uncomment these operator declarations to resolve this CS0218 /* public static bool operator true (MyClass f) { return false; } public static bool operator false (MyClass f) { return false; } */ public static implicit operator int(MyClass x) { return 0; } public static MyClass operator & (MyClass f1, MyClass f2) { return new MyClass(); } public static void Main() { MyClass f = new MyClass(); int i = f && f;   // CS0218, requires operators true and false } }  
```  
  
## 참고 항목  
 [변환 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/conversion-operators)