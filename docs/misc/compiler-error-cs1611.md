---
title: "컴파일러 오류 CS1611 | Microsoft Docs"
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
  - "CS1611"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1611"
ms.assetid: 48bfba77-6be2-4242-b1d2-98bf471b6d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1611
params 매개 변수는 ref 또는 out로 선언될 수 없습니다.  
  
 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 키워드는 [params](/dotnet/csharp/language-reference/keywords/params) 키워드와 함께 사용할 수 없습니다.  
  
 다음 샘플에서는 CS1611을 생성합니다.  
  
```  
// CS1611.cs public class MyClass { public static void Test(params ref int[] a)   // CS1611, remove ref { } public static void Main() { Test(1); } }  
```