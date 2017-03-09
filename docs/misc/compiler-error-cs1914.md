---
title: "컴파일러 오류 CS1914 | Microsoft Docs"
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
  - "CS1914"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1914"
ms.assetid: e61361b6-4660-41fd-a574-cc48e1b3873c
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1914
정적 필드 'name'은 개체 이니셜라이저에 할당할 수 없습니다.  
  
 정의에 따라 개체 이니셜라이저는 클래스의 개체 또는 인스턴스를 초기화합니다. 형식의 `static` 필드를 초기화하는 데 개체 이니셜라이저를 사용할 수는 없습니다. 생성된 클래스 인스턴스 수와 관계없이 `static` 필드의 복사본은 하나뿐입니다.  
  
### 이 오류를 해결하려면  
  
1.  형식에서 필드를 인스턴스 필드로 변경하거나 개체 이니셜라이저에서 필드를 초기화하려는 시도를 제거합니다.  
  
## 예제  
 이니셜라이저가 `static`인 `TestClass.Number` 필드를 초기화하려고 시도하므로 다음 코드에서는 CS1914를 생성합니다.  
  
```  
// cs1914.cs using System.Linq; public class TestClass { public string Message { get; set; } public static int Number { get; set; } } class Test { static void Main() { TestClass b = new TestClass() { Message = "Hello", Number = "555-1212" }; // CS1914 } }  
```