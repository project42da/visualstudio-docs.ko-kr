---
title: "컴파일러 오류 CS0068 | Microsoft Docs"
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
  - "CS0068"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0068"
ms.assetid: 9c9ac915-e12f-4ceb-8eb0-806790f11a09
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0068
'event': 인터페이스의 이벤트에는 이니셜라이저를 사용할 수 없습니다.  
  
 인터페이스의 이벤트에는 이니셜라이저를 사용할 수 없습니다. 자세한 내용은 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)을 참조하세요.  
  
 다음 샘플에서는 CS0068을 생성합니다.  
  
```  
// CS0068.cs delegate void MyDelegate(); interface I { event MyDelegate d = new MyDelegate(M.f);   // CS0068 // try the following line instead // event MyDelegate d2; } class M { event MyDelegate d = new MyDelegate(M.f); public static void f() { } public static void Main() { } }  
```