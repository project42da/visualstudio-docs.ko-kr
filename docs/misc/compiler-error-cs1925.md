---
title: "컴파일러 오류 CS1925 | Microsoft Docs"
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
  - "CS1925"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1925"
ms.assetid: b60806a5-2ccf-47f5-873b-7ac2292fdb54
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1925
컬렉션 이니셜라이저로 'type' 형식의 개체를 초기화할 수 없습니다.  
  
 컬렉션 이니셜라이저는 특정 조건을 충족하는 컬렉션 클래스에만 허용됩니다. 자세한 내용은 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)을 참조하세요. 이 오류는 또한 컬렉션 이니셜라이저 내에 중첩된 배열 이니셜라이저를 약식으로 사용하려고 할 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  해당 생성자와 메서드를 호출하여 개체를 초기화합니다.  
  
## 예제  
 다음 코드에서는 CS1925를 생성합니다.  
  
```  
// cs1925.cs public class Student { public int[] Scores; } class Test { static void Main(string[] args) { Student student = new Student { Scores = { 1, 2, 3 } }; // CS1925 } }  
```