---
title: "컴파일러 오류 CS0308 | Microsoft Docs"
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
  - "CS0308"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0308"
ms.assetid: b52ef9d2-f5b3-4baf-9a7e-bb1371e79463
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0308
제네릭이 아닌 형식 또는 메서드 'identifier'는 형식 인수와 사용할 수 없습니다.  
  
 메서드 또는 형식이 제네릭이 아니지만 형식 인수와 사용되었습니다. 이 오류를 방지하려면 대괄호와 형식 인수를 제거하거나 메서드 또는 형식을 제네릭 메서드 또는 형식으로 다시 선언합니다.  
  
 다음 예제에서는 CS0308을 생성합니다.  
  
```  
// CS0308a.cs class MyClass { public void F() {} public static void Main() { F<int>();  // CS0308 – F is not generic. // Try this instead: // F(); } }  
```  
  
 또한 다음 예제에서는 CS0308을 생성합니다. 오류를 해결하려면 "System.Collections.Generic 사용" 지시문을 사용합니다.  
  
```  
// CS0308b.cs // compile with: /t:library using System.Collections; // To resolve, uncomment the following line: // using System.Collections.Generic; public class MyStack<T> { // Store the elements of the stack: private T[] items = new T[100]; private int stack_counter = 0; // Define the iterator block: public IEnumerator<T> GetEnumerator()   // CS0308 { for (int i = stack_counter - 1 ; i >= 0; i--) yield return items[i]; } }  
  
```