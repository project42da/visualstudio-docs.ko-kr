---
title: "컴파일러 오류 CS0558 | Microsoft Docs"
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
  - "CS0558"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0558"
ms.assetid: af63b9ba-2790-4362-a49d-b69a5292a555
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0558
'operator' 사용자 정의 연산자는 static 및 public으로 선언해야 합니다.  
  
 **static** 및 **public** 액세스 [한정자](/dotnet/csharp/language-reference/keywords/modifiers)는 둘 다 사용자 정의 연산자에 지정되어야 합니다.  
  
 다음 샘플에서는 CS0558을 생성합니다.  
  
```  
// CS0558.cs namespace x { public class ii { public class iii { static implicit operator int(iii aa)   // CS0558, add public { return 0; } } public static void Main() { } } }  
```