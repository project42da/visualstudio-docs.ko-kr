---
title: "컴파일러 오류 CS0153 | Microsoft Docs"
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
  - "CS0153"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0153"
ms.assetid: 3a0791e9-0ab9-4eaa-a230-d39aabaa9d5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0153
goto case는 switch 문 내부에서만 사용할 수 있습니다.  
  
 **switch** 문 외부에서 [switch](/dotnet/csharp/language-reference/keywords/switch) 구문을 사용하려고 했습니다. 자세한 내용은 [switch](/dotnet/csharp/language-reference/keywords/switch)을 참조하세요.  
  
 다음 샘플에서는 CS0153을 생성합니다.  
  
```  
// CS0153.cs public class a { public static void Main() { goto case 5;   // CS0153 } }  
```