---
title: "컴파일러 오류 CS0620 | Microsoft Docs"
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
  - "CS0620"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0620"
ms.assetid: cadd7156-0c3c-460b-844b-c9bbfb8f62df
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0620
인덱서에는 void 형식을 사용할 수 없습니다.  
  
 [인덱서](/dotnet/csharp/programming-guide/indexers/index)의 반환 형식은 `void`일 수 없습니다. 인덱서는 값을 반환해야 합니다.  
  
 다음 샘플에서는 CS0620을 생성합니다.  
  
```  
// CS0620.cs class MyClass { public static void Main() { MyClass test = new MyClass(); System.Console.WriteLine(test[2]); } void this [int intI]   // CS0620, return type cannot be void { get { // will need to return some value } } }  
```  
  
## 참고 항목  
 [void](/dotnet/csharp/language-reference/keywords/void)