---
title: "컴파일러 오류 CS1101 | Microsoft Docs"
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
  - "CS1101"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1101"
ms.assetid: d6fc8834-eadf-4497-b442-0751895e6764
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1101
매개 변수 한정자 'ref'는 'this'와 함께 사용할 수 없습니다.  
  
 `this` 키워드가 정적 메서드의 첫 번째 매개 변수를 수정하는 경우 메서드가 확장 메서드임을 컴파일러에 알립니다. 확장 메서드의 첫 번째 매개 변수에는 다른 한정자가 필요하지 않으며 허용되지도 않습니다.  
  
## 예제  
 다음 예제에서는 CS1101을 생성합니다.  
  
```  
// cs1101.cs // Compile with: /target:library public static class Extensions { // No type parameters. public static void Test(ref this int i) {} // CS1101 // Single type parameter. public static void Test<T>(ref this T t) {}// CS1101 // Multiple type parameters. public static void Test<T,U,V>(ref this U u) {}// CS1101 }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)   
 [this](/dotnet/csharp/language-reference/keywords/this)   
 [ref](/dotnet/csharp/language-reference/keywords/ref)