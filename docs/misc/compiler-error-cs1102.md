---
title: "컴파일러 오류 CS1102 | Microsoft Docs"
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
  - "CS1102"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1102"
ms.assetid: 7de798d4-1b4b-4842-ae43-9bc83e6dc9a3
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1102
매개 변수 한정자 'out'은 'this'와 함께 사용할 수 없습니다.  
  
 `this` 키워드가 정적 메서드의 첫 번째 매개 변수를 수정하는 경우 메서드가 확장 메서드임을 컴파일러에 알립니다. 확장 메서드의 첫 번째 매개 변수에는 다른 한정자가 필요하지 않으며 허용되지도 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  첫 번째 매개 변수에서 권한이 없는 한정자를 제거합니다.  
  
## 예제  
 다음 예제에서는 CS1102를 생성합니다.  
  
```  
// cs1102.cs // Compile with: /target:library. public static class Extensions { // No type parameters. public static void Test(this out int i) {} // CS1102 //Single type parameter public static void Test<T>(this out T t) {}// CS1102 //Multiple type parameters public static void Test<T,U,V>(this out U u) {}// CS1102 }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)   
 [this](/dotnet/csharp/language-reference/keywords/this)   
 [out](/dotnet/csharp/language-reference/keywords/out)