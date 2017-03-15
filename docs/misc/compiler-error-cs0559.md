---
title: "컴파일러 오류 CS0559 | Microsoft Docs"
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
  - "CS0559"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0559"
ms.assetid: 37122001-8a55-4cf5-873b-68997e196893
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0559
\+\+ 또는 \-\- 연산자의 매개 변수 형식은 포함하는 형식이어야 합니다.  
  
 연산자 오버로드에 대한 메서드 선언은 다음의 특정 지침을 따라야 합니다. \+\+ 및 \-\- 연산자의 경우 매개 변수는 연산자가 오버로드되는 형식과 동일한 형식이어야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0559를 생성합니다.  
  
```  
// CS0559.cs // compile with: /target:library public class iii { public static implicit operator int(iii x) { return 0; } public static implicit operator iii(int x) { return null; } public static int operator ++(int aa)   // CS0559 // try the following line instead // public static iii operator ++(iii aa) { return (iii)0; } }  
```  
  
## 예제  
 다음 샘플에서는 CS0559를 생성합니다.  
  
```  
// CS0559_b.cs // compile with: /target:library public struct S { public static S operator ++(S? s) { return new S(); }   // CS0559 public static S operator --(S? s) { return new S(); }   // CS0559 } public struct T { // OK public static T operator --(T t) { return new T(); } public static T operator ++(T t) { return new T(); } public static T? operator --(T? t) { return new T(); } public static T? operator ++(T? t) { return new T(); } }  
```