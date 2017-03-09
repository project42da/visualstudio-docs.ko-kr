---
title: "컴파일러 오류 CS0073 | Microsoft Docs"
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
  - "CS0073"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0073"
ms.assetid: 579ae534-59ab-4fc5-ad7e-f87639f3f9cd
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0073
add 또는 remove 접근자에는 본문이 있어야 합니다.  
  
 [이벤트](/dotnet/csharp/language-reference/keywords/event) 정의에서 **add** 또는 **remove** 키워드는 본문이 있어야 합니다. 자세한 내용은 [이벤트](/dotnet/csharp/programming-guide/events/index)을 참조하세요.  
  
 다음 샘플에서는 CS0073을 생성합니다.  
  
```  
// CS0073.cs delegate void del(); class Test { public event del MyEvent { add;   // CS0073 // try the following lines instead // add // { //    MyEvent += value; // } remove { MyEvent -= value; } } public static void Main() { } }  
```