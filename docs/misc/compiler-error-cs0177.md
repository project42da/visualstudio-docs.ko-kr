---
title: "컴파일러 오류 CS0177 | Microsoft Docs"
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
  - "CS0177"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0177"
ms.assetid: 852a8c2a-2411-4800-af7c-4c572d9900d3
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0177
제어가 현재 메서드를 벗어나기 전에 'parameter' out 매개 변수를 할당해야 합니다.  
  
 [out](/dotnet/csharp/language-reference/keywords/out) 키워드로 표시된 매개 변수에 메서드 본문의 값이 할당되지 않았습니다. 자세한 내용은 [매개 변수 전달](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)을 참조하세요.  
  
 다음 샘플에서는 CS0177을 생성합니다.  
  
```  
// CS0177.cs public class MyClass { public static void Foo(out int i)   // CS0177 { // uncomment the following line to resolve this error //   i = 0; } public static void Main() { int x = -1; Foo(out x); } }  
```