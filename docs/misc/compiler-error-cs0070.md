---
title: "컴파일러 오류 CS0070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0070"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0070"
ms.assetid: bb0de7c6-c734-4a8f-ab62-0a50eac2a91f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0070
'event' 이벤트는 \+\= 또는 \-\=의 왼쪽에만 사용할 수 있습니다. 단 이 이벤트가 'type' 형식에서 사용될 때는 예외입니다.  
  
 정의된 클래스의 외부에서는 [이벤트](/dotnet/csharp/language-reference/keywords/event)가 참조를 추가하거나 뺄 수만 있습니다. 자세한 내용은 [이벤트](/dotnet/csharp/programming-guide/events/index)을 참조하세요.  
  
 다음 샘플에서는 CS0070을 생성합니다.  
  
```  
// CS0070.cs using System; public delegate void EventHandler(); public class A { public event EventHandler Click; public static void OnClick() { EventHandler eh; A a = new A(); eh = a.Click; } public static void Main() { } } public class B { public int Foo () { EventHandler eh = new EventHandler(A.OnClick); A a = new A(); eh = a.Click;   // CS0070 // try the following line instead // a.Click += eh; return 1; } }  
```