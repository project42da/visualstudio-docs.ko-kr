---
title: "컴파일러 오류 CS0180 | Microsoft Docs"
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
  - "CS0180"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0180"
ms.assetid: a21bf0a2-ed5a-4ddd-88d3-240babc5888a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0180
'member'는 extern이면서 abstract일 수 없습니다.  
  
 [abstract](/dotnet/csharp/language-reference/keywords/abstract) 및 [extern](/dotnet/csharp/language-reference/keywords/extern) 키워드는 함께 사용할 수 없습니다.`extern` 키워드는 멤버가 파일 외부에서 정의되었음을 의미하고, **abstract**는 구현이 파생 클래스에서 제공되었음을 의미합니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
 다음 샘플에서는 CS0180을 생성합니다.  
  
```  
// CS0180.cs namespace MyNamespace { public class MyClass { public extern abstract int Foo(int a);   // CS0180 public static void Main() { } } }  
```