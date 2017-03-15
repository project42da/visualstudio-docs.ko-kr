---
title: "컴파일러 오류 CS0074 | Microsoft Docs"
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
  - "CS0074"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0074"
ms.assetid: 9395c532-3934-4553-8e41-042bfe3399ce
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0074
'event': 추상 이벤트에는 이니셜라이저를 사용할 수 없습니다.  
  
 [event](/dotnet/csharp/language-reference/keywords/event)가 **abstract**로 표시되는 경우 초기화할 수 없습니다. 자세한 내용은 [이벤트](/dotnet/csharp/programming-guide/events/index)을 참조하세요.  
  
 다음 샘플에서는 CS0074를 생성합니다.  
  
```  
// CS0074.cs delegate void D(); abstract class Test { public abstract event D e = null;   // CS0074 // try the following line instead // public abstract event D e; public static void Main() { } }  
```