---
title: "컴파일러 오류 CS0448 | Microsoft Docs"
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
  - "CS0448"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0448"
ms.assetid: f577ab4c-1c8c-4a10-80a8-9ba9f66c3d25
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0448
\+\+ 또는 \-\- 연산자의 반환 형식은 포함하는 형식이거나 포함하는 형식에서 파생되어야 합니다.  
  
 `++` 또는 `--` 연산자를 재정의하는 경우, 포함하는 형식과 동일한 형식을 반환하거나 포함하는 형식에서 파생된 형식을 반환해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0448을 생성합니다.  
  
```  
// CS0448.cs class C5 { public static int operator ++(C5 c) { return null; }   // CS0448 public static C5 operator --(C5 c) { return null; }   // OK public static void Main() {} }  
```  
  
## 예제  
 다음 샘플에서는 CS0448을 생성합니다.  
  
```  
// CS0448_b.cs public struct S { public static S? operator ++(S s) { return new S(); }   // CS0448 public static S? operator --(S s) { return new S(); }   // CS0448 } public struct T { // OK public static T operator --(T t) { return new T(); } public static T operator ++(T t) { return new T(); } public static T? operator --(T? t) { return new T(); } public static T? operator ++(T? t) { return new T(); } public static void Main() {} }  
```