---
title: "컴파일러 오류 CS0238 | Microsoft Docs"
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
  - "CS0238"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0238"
ms.assetid: 9b50c6e2-2c3f-431d-bdb7-557b0ec51626
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0238
'member'는 override가 아니므로 sealed가 될 수 없습니다.  
  
 [override](/dotnet/csharp/language-reference/keywords/override)로 표시되지 않은 멤버에 [sealed](/dotnet/csharp/language-reference/keywords/sealed)를 사용했습니다. 자세한 내용은 [상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)을 참조하세요.  
  
 다음 샘플에서는 CS0238을 생성합니다.  
  
```  
// CS0238.cs abstract class MyClass { public abstract void f(); } class MyClass2 : MyClass { public static void Main() { } public sealed void f() // CS0238 // Try the following definition instead: // public override sealed void f() { } }  
```