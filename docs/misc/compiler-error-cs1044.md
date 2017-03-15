---
title: "컴파일러 오류 CS1044 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1044"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1044"
ms.assetid: 18fc1ff5-8b97-4c31-99a1-5985b8e58024
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1044
for 문, using 문, fixed 문, 선언문 등에는 둘 이상의 형식을 사용할 수 없습니다.  
  
 컴파일러에서 잘못된 문을 발견했습니다.  
  
 다음 샘플에서는 CS1044를 생성합니다.  
  
```  
// CS1044.cs using System; public class MyClass : IDisposable { public void Dispose() { Console.WriteLine("Res1.Dispose()"); } public static void Main() { using (MyClass mc1 = new MyClass(), MyClass mc2 = new MyClass())   // CS1044, remove an instantiation { } } }  
```