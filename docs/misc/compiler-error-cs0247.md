---
title: "컴파일러 오류 CS0247 | Microsoft Docs"
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
  - "CS0247"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0247"
ms.assetid: 95a147bb-3c67-45b7-b816-4fcf7503af06
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0247
stackalloc에는 음수 크기를 사용할 수 없습니다.  
  
 음수가 [stackalloc](/dotnet/csharp/language-reference/keywords/stackalloc) 문에 전달되었습니다.  
  
 다음 샘플에서는 CS0247을 생성합니다.  
  
```  
// CS0247.cs // compile with: /unsafe public class MyClass { unsafe public static void Main() { int *p = stackalloc int [-30];   // CS0247 } }  
```