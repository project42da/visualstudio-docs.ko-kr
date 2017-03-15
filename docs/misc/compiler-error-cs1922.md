---
title: "컴파일러 오류 CS1922 | Microsoft Docs"
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
  - "CS1922"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1922"
ms.assetid: a4098a25-6581-4966-b61d-318cd12f76d3
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1922
컬렉션 이니셜라이저의 'type' 형식이 System.Collections.IEnumerable을 구현해야 합니다.  
  
 형식과 함께 컬렉션 이니셜라이저를 사용하려면 형식이 `IEnumerable`을 구현해야 합니다. 이 오류는 개체 이니셜라이저를 사용하려다가 실수로 컬렉션 이니셜라이저 구문을 사용하는 경우에 발생할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   형식이 컬렉션을 나타내지 않는 경우 컬렉션 이니셜라이저 구문 대신 개체 이니셜라이저 구문을 사용합니다.  
  
-   형식이 컬렉션을 나타내는 경우 컬렉션 이니셜라이저를 사용하여 해당 형식의 개체를 초기화하기 전에 `IEnumerable`를 구현하도록 수정합니다.  
  
-   형식이 컬렉션을 나타내고 소스 코드에 액세스할 수 없는 경우 클래스 생성자 또는 다른 초기화 메서드를 사용하여 해당 요소를 초기화합니다.  
  
## 예제  
 다음 코드에서는 CS1922를 생성합니다.  
  
```  
// cs1922.cs public class Test { public static void Main() { // Collection initializer. var tc = new TestClass  {1,"hello"} ; // CS1922 // Object initalizer. var tc2 = new TestClass { memberA = 1, memberB = "hello" }; // OK } } public class TestClass { public int memberA { get; set; } public string memberB { get; set; } }  
  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)