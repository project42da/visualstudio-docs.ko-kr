---
title: "컴파일러 오류 CS1576 | Microsoft Docs"
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
  - "CS1576"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1576"
ms.assetid: 3e39cb80-e7de-4c78-a22a-57e267121a96
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1576
\#line 지시문에 지정한 줄 번호가 없거나 잘못되었습니다.  
  
 컴파일러가 [\#line](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-line) 지시문에 전달된 값에서 오류를 발견했습니다.  
  
 다음 샘플에서는 CS1576을 생성합니다.  
  
```  
// CS1576.cs public class MyClass { static void Main() { #line "abc.sc"         // CS1576 // try the following line instead //#line  101 "abc.sc" intt i;  // error will be reported on line 101 } }  
```