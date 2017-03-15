---
title: "컴파일러 오류 CS0225 | Microsoft Docs"
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
  - "CS0225"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0225"
ms.assetid: 0b0cd72b-c47a-44d1-9b27-d1a1fad06807
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0225
매개 변수 배열은 1차원 배열이어야 합니다.  
  
 [params](/dotnet/csharp/language-reference/keywords/params) 키워드를 사용하는 경우 데이터 형식의 1차원 배열을 지정해야 합니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0225를 생성합니다.  
  
```  
// CS0225.cs public class MyClass { public static void TestParams(params int a)   // CS0225 // try the following line instead // public static void TestParams(params int[] a) { } public static void Main() { TestParams(1); } }  
```