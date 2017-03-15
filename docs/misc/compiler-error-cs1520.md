---
title: "컴파일러 오류 CS1520 | Microsoft Docs"
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
  - "CS1520"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1520"
ms.assetid: 1aeeee83-52a6-45dc-b197-a9a6de3a220c
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1520
메서드에는 반환 형식이 있어야 합니다.  
  
 클래스, 구조체 또는 인터페이스에서 선언된 메서드에는 명시적인 반환 형식이 있어야 합니다. 다음 예제에서 Square 메서드에는 반환 값 [string](/dotnet/csharp/language-reference/keywords/string)이 있습니다.  
  
```  
class Test { string IntToString(int i) { return i.ToString(); } }  
```  
  
 다음 샘플에서는 CS1520을 생성합니다.  
  
```  
// CS1520a.cs public class x { // Method declaration missing a return type MyMethod()   // CS1520 {} // Add the desired return type: // void MyMethod2() // { } public static void Main() { } }  
```  
  
 또는 다음 샘플과 같이 생성자 이름의 대\/소문자가 클래스 또는 구조체 선언 이름의 대\/소문자와 다른 경우에도 이 오류가 발생할 수 있습니다. 이름이 클래스 이름과 정확하게 일치하지 않으므로 컴파일러는 이를 생성자가 아닌 정규 메서드로 해석하고 오류를 생성합니다.  
  
```  
// CS1520b.cs public class Class1 { // Should be Class1, not class1 public class1()   // CS1520 { } static void Main() { } }  
```  
  
## 참고 항목  
 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)   
 [생성자](/dotnet/csharp/programming-guide/classes-and-structs/constructors)