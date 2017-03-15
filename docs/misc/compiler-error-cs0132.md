---
title: "컴파일러 오류 CS0132 | Microsoft Docs"
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
  - "CS0132"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0132"
ms.assetid: e8ad1281-2912-4b6a-b2af-a319a23ddd16
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0132
'constructor': 정적 생성자에는 매개 변수가 없어야 합니다.  
  
 [정적](/dotnet/csharp/language-reference/keywords/static) 생성자를 하나 이상의 매개 변수와 함께 선언할 수 없습니다. 자세한 내용은 [생성자](/dotnet/csharp/programming-guide/classes-and-structs/constructors)을 참조하세요.  
  
 다음 샘플에서는 CS0132를 생성합니다.  
  
```  
// CS0132.cs namespace MyNamespace { public class MyClass { public MyClass(int i) { } } public class MyClass2 : MyClass { static MyClass2(int i)   // CS0132 { } } }  
```