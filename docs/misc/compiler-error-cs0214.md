---
title: "컴파일러 오류 CS0214 | Microsoft Docs"
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
  - "CS0214"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0214"
ms.assetid: be1ef909-a53e-485f-a79b-b1cc56cead15
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0214
포인터와 고정 크기 버퍼는 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.  
  
 포인터는 [안전하지 않은](/dotnet/csharp/language-reference/keywords/unsafe) 키워드에만 사용할 수 있습니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
 다음 샘플에서는 CS0214를 생성합니다.  
  
```  
// CS0214.cs // compile with: /target:library /unsafe public struct S { public int a; } public class MyClass { public static void Test() { S s = new S(); S * s2 = &s;    // CS0214 s2->a = 3;      // CS0214 s.a = 0; } // OK unsafe public static void Test2() { S s = new S(); S * s2 = &s; s2->a = 3; s.a = 0; } }  
```