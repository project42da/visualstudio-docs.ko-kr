---
title: "컴파일러 오류 CS1900 | Microsoft Docs"
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
  - "CS1900"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1900"
ms.assetid: 08141138-bfea-4af3-a9a0-ec54cf2caa13
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1900
경고 수준은 0부터 4까지의 범위에 있어야 합니다.  
  
 [\/warn](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option) 컴파일러 옵션은 5가지 값\(0, 1, 2, 3 또는 4\) 중 하나만 사용할 수 있습니다.**\/warn**에 다른 값을 전달하면 CS1900이 발생합니다.  
  
 다음 샘플에서는 CS1900을 생성합니다.  
  
```  
// CS1900.cs // compile with: /W:5 // CS1900 expected class x { public static void Main() { } }  
```