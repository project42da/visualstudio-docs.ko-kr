---
title: "컴파일러 오류 CS0239 | Microsoft Docs"
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
  - "CS0239"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0239"
ms.assetid: 2e07bbc2-03a9-44b2-b321-477ca95fff8c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0239
'member': 'inherited member' 상속된 멤버가 봉인되어 있으므로 재정의할 수 없습니다.  
  
 멤버가 [봉인된](/dotnet/csharp/language-reference/keywords/sealed) 상속된 멤버를 [재정의](/dotnet/csharp/language-reference/keywords/override)할 수 없습니다. 자세한 내용은 [Checked 및 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)을 참조하세요.  
  
 다음 샘플에서는 CS0239를 생성합니다.  
  
```  
// CS0239.cs abstract class MyClass { public abstract void f(); } class MyClass2 : MyClass { public static void Main() { } public override sealed void f() { } } class MyClass3 : MyClass2 { public override void f()   // CS0239 // Try the following definition instead: // public new void f() { } }  
```