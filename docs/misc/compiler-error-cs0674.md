---
title: "컴파일러 오류 CS0674 | Microsoft Docs"
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
  - "CS0674"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0674"
ms.assetid: 9ebfac30-6de8-4503-b4f0-d79f7398e3d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0674
System.ParamArrayAttribute'를 사용하지 않고, 대신 'params' 키워드를 사용하세요.  
  
 C\# 컴파일러에서는 <xref:System.ParamArrayAttribute?displayProperty=fullName>를 사용할 수 없습니다. 대신 [params](/dotnet/csharp/language-reference/keywords/params)를 사용하세요.  
  
 다음 샘플에서는 CS0674를 생성합니다.  
  
```  
// CS0674.cs using System; public class MyClass { public static void UseParams([ParamArray] int[] list)   // CS0674 // try the following line instead // public static void UseParams(params int[] list) { for ( int i = 0 ; i < list.Length ; i++ ) Console.WriteLine(list[i]); Console.WriteLine(); } public static void Main() { UseParams(1, 2, 3); } }  
```