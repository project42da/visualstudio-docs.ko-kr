---
title: "컴파일러 오류 CS0113 | Microsoft Docs"
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
  - "CS0113"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0113"
ms.assetid: 43c5c0b7-67c0-45c1-8363-21c844c094f3
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0113
override로 표시된 'function' 멤버는 new 또는 virtual로 표시할 수 없습니다.  
  
 [new](/dotnet/csharp/language-reference/keywords/new) 및 [override](/dotnet/csharp/language-reference/keywords/override) 키워드로 메서드를 표시할 수 없습니다.  
  
 다음 샘플에서는 CS0113을 생성합니다.  
  
```  
// CS0113.cs namespace MyNamespace { abstract public class MyClass { public abstract void Foo(); } public class MyClass2 : MyClass { override new public void Foo()   // CS0113, remove new keyword { } public static int Main() { return 0; } } }  
```