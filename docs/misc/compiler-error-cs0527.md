---
title: "컴파일러 오류 CS0527 | Microsoft Docs"
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
  - "CS0527"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0527"
ms.assetid: 1acd244b-c55b-424f-b038-a130d65b8685
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0527
인터페이스 목록에 있는 'type' 형식이 인터페이스가 아닙니다.  
  
 다른 인터페이스에서 [struct](/dotnet/csharp/language-reference/keywords/struct) 또는 [interface](/dotnet/csharp/language-reference/keywords/interface)를 상속할 수 있지만 다른 형식에서는 상속할 수 없습니다.  
  
 다음 샘플에서는 CS0527을 생성합니다.  
  
```  
// CS0527.cs // compile with: /target:library public struct clx : int {}   // CS0527 int not an interface  
```