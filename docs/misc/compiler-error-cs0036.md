---
title: "컴파일러 오류 CS0036 | Microsoft Docs"
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
  - "CS0036"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0036"
ms.assetid: ddbaa36e-473b-4283-a13c-44a71ae5da2e
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0036
out 매개 변수에는 '\[In\]' 특성을 사용할 수 없습니다.  
  
 현재 **In** 특성은 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수에서 허용되지 않습니다.  
  
 다음 샘플에서는 CS0036을 생성합니다.  
  
```  
// CS0036.cs using System; using System.Runtime.InteropServices; public class MyClass { public static void TestOut([In] out char TestChar)   // CS0036 // try the following line instead // public static void TestOut(out char TestChar) { TestChar = 'b'; Console.WriteLine(TestChar); } public static void Main() { char i;           //variable to receive the value TestOut(out i);   // the arg must be passed as out Console.WriteLine(i); } }  
```