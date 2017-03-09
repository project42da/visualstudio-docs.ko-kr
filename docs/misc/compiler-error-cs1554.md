---
title: "컴파일러 오류 CS1554 | Microsoft Docs"
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
  - "CS1554"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1554"
ms.assetid: 81e8d4ac-cdbf-4b75-8932-0bc271a8405c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1554
선언이 잘못되었습니다. 대신 '\<type\> operator op \(...'을 사용하세요.  
  
 사용자 정의 [operator](/dotnet/csharp/language-reference/keywords/operator)에 대한 반환 형식은 키워드 연산자 앞에 와야 합니다.  
  
 다음 샘플에서는 CS1554를 생성합니다.  
  
```  
// CS1554.cs class MyClass { public static operator ++ MyClass (MyClass f)    // CS1554 // try the following line instead // public static MyClass operator ++ (MyClass f) { return new MyClass (); } public static void Main() { } }  
```