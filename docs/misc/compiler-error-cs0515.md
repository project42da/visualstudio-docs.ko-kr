---
title: "컴파일러 오류 CS0515 | Microsoft Docs"
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
  - "CS0515"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0515"
ms.assetid: 0f8c0253-218d-4c21-b22c-fa5802ba4e7f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0515
'function': 정적 생성자에서는 액세스 한정자를 사용할 수 없습니다.  
  
 정적 생성자에는 [액세스 한정자](/dotnet/csharp/language-reference/keywords/modifiers)를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0515를 생성합니다.  
  
```  
// CS0515.cs public class Clx { public static void Main() { } } public class Clz { public static Clz()   // CS0515, remove public keyword { } }  
```