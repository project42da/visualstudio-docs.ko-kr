---
title: "컴파일러 오류 CS1654 | Microsoft Docs"
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
  - "CS1654"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1654"
ms.assetid: 471c1298-1908-449d-b765-8dc3cd81a11d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1654
'read\-only variable type'이므로 'variable'의 멤버를 수정할 수 없습니다.  
  
 이 오류는 특수 구문에 있기 때문에 읽기 전용인 변수의 멤버를 수정하려는 경우에 발생합니다.  
  
 이 오류가 발생하는 하나의 일반적인 영역은 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 루프 내부입니다. 컬렉션 요소의 값을 수정하는 것은 컴파일 시간 오류입니다. 따라서 [구조체](/dotnet/csharp/programming-guide/classes-and-structs/structs)를 포함하여 [값 형식](/dotnet/csharp/language-reference/keywords/value-types)인 요소를 수정할 수 없습니다. 해당 요소가 [참조 형식](/dotnet/csharp/language-reference/keywords/reference-types)인 컬렉션에서는 각 요소의 액세스할 수 있는 멤버를 수정할 수 있지만 전체 요소를 추가, 제거 또는 바꾸려고 하면 [Compiler Error CS1656](/dotnet/csharp/language-reference/compiler-messages/cs1656)이 생성됩니다.  
  
## 예제  
 다음 예제에서는 `Book`이 `struct`이므로 CS1654 오류를 생성합니다. 오류를 해결하려면 `struct`를 [클래스](/dotnet/csharp/language-reference/keywords/class)로 변경합니다.  
  
```  
using System.Collections.Generic; using System.Text; namespace CS1654 { struct Book { public string Title; public string Author; public double Price; public Book(string t, string a, double p) { Title=t; Author=a; Price=p; } } class Program { List<Book> list; static void Main(string[] args) { //Use a collection initializer to initialize the list Program prog = new Program(); prog.list = new List<Book>(); prog.list.Add(new Book ("The C# Programming Language", "Hejlsberg, Wiltamuth, Golde", 29.95)); prog.list.Add(new Book ("The C++ Programming Language", "Stroustrup", 29.95)); prog.list.Add(new Book ("The C Programming Language", "Kernighan, Ritchie", 29.95)); foreach(Book b in prog.list) { //Compile error if Book is a struct //Make Book a class to modify its members b.Price +=9.95; // CS1654 } } } }  
  
```