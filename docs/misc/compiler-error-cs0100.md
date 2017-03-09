---
title: "컴파일러 오류 CS0100 | Microsoft Docs"
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
  - "CS0100"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0100"
ms.assetid: b49e4846-2a82-48ed-9ca8-953eb5c1baaa
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0100
'parameter name' 매개 변수 이름이 중복되었습니다.  
  
 메서드 선언이 동일한 매개 변수 이름을 두 번 이상 사용했습니다. 메서드 선언에서 매개 변수 이름은 고유해야 합니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
 다음 샘플에서는 CS0100을 생성합니다.  
  
```  
// CS0100.cs namespace x { public class a { public static void f(int i, char i)   // CS0100 // try the following line instead // public static void f(int i, char j) { } public static void Main() { } } }  
```