---
title: "컴파일러 오류 CS0677 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0677"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0677"
ms.assetid: 6a4a3703-9b44-4c4f-a564-8b437b1cb6b8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0677
'variable': volatile 필드는 'type' 형식일 수 없습니다.  
  
 `volatile` 키워드로 선언된 필드는 다음 형식 중 하나여야 합니다.  
  
-   임의 참조 형식  
  
-   임의 포인터 형식\(`unsafe` 컨텍스트\)  
  
-   `sbyte`, **byte**, **short**, `ushort`, `int`, `uint`, `char`, **float**, `bool` 형식  
  
-   위 형식 중 하나를 기반으로 하는 열거 형식  
  
 다음 샘플에서는 CS0677을 생성합니다.  
  
```  
// CS0677.cs class TestClass { private volatile long i;   // CS0677 public static void Main() { } }  
```