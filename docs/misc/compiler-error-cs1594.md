---
title: "컴파일러 오류 CS1594 | Microsoft Docs"
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
  - "CS1594"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1594"
ms.assetid: f949a992-27a3-470d-b512-e590e5170af3
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1594
'delegate' 대리자에 잘못된 인수가 있습니다.  
  
 [delegate](/dotnet/csharp/language-reference/keywords/delegate) 호출에 전달된 인수 형식이 대리자 선언의 매개 변수 형식에 맞지 않습니다.  
  
 다음 샘플에서는 CS1594를 생성합니다.  
  
```  
// CS1594.cs using System; delegate string func(int i);   // declare delegate class a { public static void Main() { func dt = new func(z); x(dt); } public static string z(int j) { Console.WriteLine(j); return j.ToString(); } public static void x(func hello) { hello("8");   // CS1594 // try the following line instead // hello(8); } }  
```