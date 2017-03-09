---
title: "컴파일러 오류 CS1558 | Microsoft Docs"
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
  - "CS1558"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1558"
ms.assetid: ee603d66-007e-4782-9285-7ff031975f0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1558
'class'에 적합한 정적 Main 메서드가 없습니다.  
  
 [\/main](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) 컴파일러 옵션에서 **Main** 메서드를 찾을 클래스를 지정했습니다. 그러나 [Main](/dotnet/csharp/programming-guide/main-and-command-args/main-and-command-line-arguments) 메서드가 올바르게 정의되지 않았습니다.  
  
 다음 예제에서는 잘못된 반환 형식으로 인해 CS1558을 생성합니다.  
  
```  
// CS1558.cs // compile with: /main:MyNamespace.MyClass namespace MyNamespace { public class MyClass { public static float Main() { return 0.0; // CS1558 because the return type is a float. } } }  
```