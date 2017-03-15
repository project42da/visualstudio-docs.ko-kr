---
title: "컴파일러 오류 CS0837 | Microsoft Docs"
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
  - "CS0837"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0837"
ms.assetid: cbde45dc-222c-4bfe-8814-856476319d37
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0837
"is" 또는 "as" 연산자의 첫 번째 피연산자는 람다 식 또는 무명 메서드가 될 수 없습니다.  
  
 람다 식과 무명 메서드는 [is](/dotnet/csharp/language-reference/keywords/is) 또는 [as](/dotnet/csharp/language-reference/keywords/as)의 왼쪽에 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   오류가 `is` 연산자와 관련된 경우 `is`는 값과 형식을 사용하며 참조, boxing 또는 unboxing 변환을 통해 값을 해당 형식으로 변환할 수 있는지를 알립니다. 람다는 값이 아니며 참조, boxing 또는 unboxing 변환이 없으므로 람다는 `is`의 후보가 아닙니다.  
  
-   코드에서 `as`를 잘못 사용하는 경우 캐스트로 변경하여 수정합니다.  
  
## 예제  
 다음 예제에서는 CS0837을 생성합니다.  
  
```  
// cs0837.cs namespace TestNamespace { public delegate void Del(); class Test { static int Main() { bool b1 = (() => { }) is Del;   // CS0837 bool b2 = delegate() { } is Del;// CS0837 Del d1 = () => { } as Del;      // CS0837 Del d2 = delegate() { } as Del; // CS0837 return 1; } } }  
```