---
title: "컴파일러 오류 CS0193 | Microsoft Docs"
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
  - "CS0193"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0193"
ms.assetid: 7b60fd99-9eee-4d61-ad75-585a16e22e96
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0193
\* 또는 \-\> 연산자는 포인터에 적용되어야 합니다.  
  
 **\*** 또는 **\-\>** 연산자를 포인터가 아닌 형식과 함께 사용했습니다. 자세한 내용은 [포인터 형식](/dotnet/csharp/programming-guide/unsafe-code-pointers/pointer-types)을 참조하세요.  
  
 다음 샘플에서는 CS0193을 생성합니다.  
  
```  
// CS0193.cs using System; public struct Age { public int AgeYears; public int AgeMonths; public int AgeDays; } public class MyClass { public static void SetAge(ref Age anAge, int years, int months, int days) { anAge->Months = 3;   // CS0193, anAge is not a pointer // try the following line instead // anAge.AgeMonths = 3; } public static void Main() { Age MyAge = new Age(); Console.WriteLine(MyAge.AgeMonths); SetAge(ref MyAge, 22, 4, 15); Console.WriteLine(MyAge.AgeMonths); } }  
```