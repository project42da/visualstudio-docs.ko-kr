---
title: "컴파일러 오류 CS0751 | Microsoft Docs"
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
  - "CS0751"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0751"
ms.assetid: 2ebaed5f-d3ca-452f-8fce-f3299b84360a
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0751
부분 메서드\(Partial Method\)는 partial 클래스 또는 partial 구조체 내에 선언해야 합니다.  
  
 [부분](/dotnet/csharp/language-reference/keywords/partial-method) 메서드\(Partial Method\)는 partial 클래스 또는 partial 구조체 안에 캡슐화되지 않으면 선언할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  `partial` 한정자를 메서드에서 제거하고 구현을 제공하거나 `partial` 한정자를 바깥쪽 클래스 또는 구조체에 추가합니다.  
  
## 예제  
 다음 예제에서는 CS0751을 생성합니다.  
  
```  
// cs0751.cs using System; public class C { partial void Part(); // CS0751 public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)