---
title: "컴파일러 오류 CS1553 | Microsoft Docs"
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
  - "CS1553"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1553"
ms.assetid: aec64251-b4ac-45c0-b143-7ebda138af6e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1553
선언이 잘못되었습니다. 대신 'modifier operator \<dest\-type\> \(...'을 사용하세요.  
  
 [operator](/dotnet/csharp/language-reference/keywords/operator)에 대한 반환 형식은 매개 변수 목록 바로 앞에 있어야 하고 *한정자*는 `implicit` 또는 **explicit**이어야 합니다.  
  
 다음 샘플에서는 CS1553을 생성합니다.  
  
```  
// CS1553.cs class MyClass { public static int implicit operator (MyClass f)   // CS1553 // try the following line instead // public static implicit operator int (MyClass f) { return 6; } public static void Main() { } }  
```