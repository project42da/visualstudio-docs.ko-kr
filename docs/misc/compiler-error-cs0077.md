---
title: "컴파일러 오류 CS0077 | Microsoft Docs"
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
  - "CS0077"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0077"
ms.assetid: 55d3d290-d172-41a3-b326-ebf5a0a7e81f
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0077
as 연산자는 참조 형식 또는 nullable 형식과 함께 사용해야 합니다. 'int'는 null을 허용하지 않는 값 형식입니다.  
  
 [as](/dotnet/csharp/language-reference/keywords/as) 연산자가 [값 형식](/dotnet/csharp/language-reference/keywords/value-types)으로 전달되었습니다.`as`는 [null](/dotnet/csharp/language-reference/keywords/null)을 반환할 수 있기 때문에 [참조 형식](/dotnet/csharp/language-reference/keywords/reference-types) 또는 nullable 형식만 전달할 수 있습니다. nullable 형식에 대한 자세한 내용은 [nullable 형식](/dotnet/csharp/programming-guide/nullable-types/index)을 참조하세요.  
  
 다음 샘플에서는 CS0077을 생성합니다.  
  
```  
// CS0077.cs using System; class C { } struct S { } class M { public static void Main() { object o1, o2; C c; S s; o1 = new C(); o2 = new S(); s = o2 as S;  // CS0077, S is not a reference type. // try the following line instead // c = o1 as C; } }  
```