---
title: "컴파일러 오류 CS1912 | Microsoft Docs"
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
  - "CS1912"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1912"
ms.assetid: 6205420e-01b9-4470-89f9-5924f1e49108
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1912
'name' 멤버의 초기화가 중복되었습니다.  
  
 개체 이니셜라이저는 각 멤버를 한 번만 초기화할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  개체 이니셜라이저에서 두 번째 멤버 초기화를 제거합니다.  
  
## 예제  
 `memberA`가 두 번 초기화되었기 때문에 다음 코드에서는 CS1912를 생성합니다.  
  
```  
// cs1912.cs using System.Linq; public class TestClass { public int memberA { get; set; } public int memberB { get; set; } } public class Test { static void Main() { TestClass tc = new TestClass() { memberA = 5, memberA = 6, memberB = 2}; // CS1912 } }  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)