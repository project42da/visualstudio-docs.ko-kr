---
title: "컴파일러 오류 CS1902 | Microsoft Docs"
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
  - "CS1902"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1902"
ms.assetid: 120c5978-9ebc-4ec1-bcec-f840af6fdf5d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1902
\/debug에 대한 'option' 옵션이 잘못되었습니다. full 또는 pdbonly여야 합니다.  
  
 잘못된 옵션이 [\/debug](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) 컴파일러 옵션에 전달되었습니다.  
  
 다음 샘플에서는 CS1902를 생성합니다.  
  
```  
// CS1902.cs // compile with: /debug:x // CS1902 expected class x { public static void Main() { } }  
```