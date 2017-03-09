---
title: "컴파일러 오류 CS1578 | Microsoft Docs"
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
  - "CS1578"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1578"
ms.assetid: 8356cd33-5acc-4db7-8bbd-2d25f9d7728e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1578
파일 이름, 한 줄로 된 주석 또는 줄 끝\(EOL\)이 필요합니다.  
  
 [\#line](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-line) 지시문 뒤에는 큰따옴표로 묶은 파일 이름 또는 한 줄로 된 주석만 허용됩니다.  
  
 다음 샘플에서는 CS1578을 생성합니다.  
  
```  
// CS1578.cs class MyClass { static void Main() { #line 101 abc.cs   // CS1578 // try the following line instead //#line 101 "abc.cs" intt i;          // error will be reported on line 101 } }  
```