---
title: "컴파일러 오류 CS0066 | Microsoft Docs"
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
  - "CS0066"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0066"
ms.assetid: 9b50b49b-78b8-4562-8839-d59e5edbec6b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0066
'event': 이벤트는 대리자 형식이어야 합니다.  
  
 이벤트 키워드에는 [delegate](/dotnet/csharp/language-reference/keywords/delegate) 형식이 필요합니다. 자세한 내용은 [이벤트](/dotnet/csharp/programming-guide/events/index) 및 [대리자](/dotnet/csharp/programming-guide/delegates/index)를 참조하세요.  
  
 다음 샘플에서는 CS0066을 생성합니다.  
  
```  
// CS0066.cs using System; public class EventHandler { } // to fix the error, remove the event declaration and the // EventHandler class declaration, and uncomment the following line // public delegate void EventHandler(); public class a { public event EventHandler Click;   // CS0066 private void TestMethod() { if (Click != null) Click(); } public static void Main() { } }  
```