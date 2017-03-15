---
title: "컴파일러 오류 CS1106 | Microsoft Docs"
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
  - "CS1106"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1106"
ms.assetid: 3585600a-6b2c-47aa-a418-ef049f07c107
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1106
확장 메서드는 제네릭이 아닌 정적 클래스에 정의해야 합니다.  
  
 확장 메서드는 제네릭이 아닌 정적 클래스에 정적 메서드로 정의해야 합니다.  
  
## 예제  
 다음 예제에서는 `Extensions` 클래스가 `static`으로 정의되지 않았기 때문에 CS1106을 생성합니다.  
  
```  
// cs1106.cs public class Extensions // CS1106 { public  static void Test<T>(this System.String s) {} }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)   
 [static](/dotnet/csharp/language-reference/keywords/static)