---
title: "컴파일러 오류 CS1954 | Microsoft Docs"
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
  - "CS1954"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1954"
ms.assetid: bdec399e-c43d-46d3-a01b-ef3572786fe5
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1954
컬렉션 이니셜라이저 요소에 가장 일치하는 오버로드된 메서드 'method'를 사용할 수 없습니다. 컬렉션 이니셜라이저 'Add' 메서드는 ref 또는 out 매개 변수를 사용할 수 없습니다.  
  
 컬렉션 이니셜라이저를 사용하여 컬렉션 클래스가 초기화되려면 클래스에 `ref` 또는 `out` 매개 변수가 아닌 `public` `Add` 메서드가 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
-   컬렉션 클래스의 소스 코드를 수정할 수 있는 경우 `ref` 또는 `out` 매개 변수를 사용하지 않는 `Add` 메서드를 제공합니다.  
  
-   컬렉션 클래스를 수정할 수 없는 경우 제공되는 생성자를 사용하여 초기화합니다. 컬렉션 이니셜라이저를 함께 사용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 `MyList`에 있는 `Add` 목록의 유일하게 사용할 수 있는 오버로드에 `ref` 매개 변수가 있으므로 CS1954를 생성합니다.  
  
```  
// cs1954.cs using System.Collections.Generic; class MyList<T> : IEnumerable<T> { List<T> _list; public void Add(ref T item) { _list.Add(item); } public System.Collections.Generic.IEnumerator<T> GetEnumerator() { int index = 0; T current = _list[index]; while (current != null) { yield return _list[index++]; } } System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator() { return GetEnumerator(); } } public class MyClass { public string tree { get; set; } } class Program { static void Main(string[] args) { MyList<MyClass> myList = new MyList<MyClass> { new MyClass { tree = "maple" } }; // CS1954 } }  
  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)