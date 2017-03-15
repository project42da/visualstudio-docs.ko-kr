---
title: "컴파일러 오류 CS0133 | Microsoft Docs"
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
  - "CS0133"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0133"
ms.assetid: b5be456f-824d-4e6d-802b-0b1b5889efbd
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0133
'variable'에 할당할 식은 상수여야 합니다.  
  
 [const](/dotnet/csharp/language-reference/keywords/const) 변수는 상수가 아닌 식을 해당 값으로 사용할 수 없습니다. 자세한 내용은 [상수](/dotnet/csharp/programming-guide/classes-and-structs/constants)을 참조하세요.  
  
 다음 샘플에서는 CS0133을 생성합니다.  
  
```  
// CS0133.cs public class MyClass { public const int i = c;   // CS0133, c is not constant public static int c = i; // try the following line instead // public const int i = 6; public static void Main() { } }  
```