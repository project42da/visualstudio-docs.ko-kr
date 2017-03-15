---
title: "컴파일러 오류 CS0065 | Microsoft Docs"
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
  - "CS0065"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0065"
ms.assetid: 49ca30a8-513a-40ed-aa0c-eb696a25b91f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0065
'event': 이벤트 속성에는 add 및 remove 접근자가 둘 다 있어야 합니다.  
  
 필드가 아닌 이벤트에는 두 액세스 메서드가 모두 있어야 합니다.  
  
 다음 샘플에서는 CS0065를 생성합니다.  
  
```  
// CS0065.cs using System; public delegate void Eventhandler(object sender, int e); public class MyClass { public event EventHandler Click   // CS0065, { // to fix, uncomment the add and remove definitions /* add { Click += value; } remove { Click -= value; } */ } public static void Main() { } }  
```  
  
## 참고 항목  
 [이벤트](/dotnet/csharp/programming-guide/events/index)