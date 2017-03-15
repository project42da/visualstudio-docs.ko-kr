---
title: "컴파일러 오류 CS0172 | Microsoft Docs"
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
  - "CS0172"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0172"
ms.assetid: 1272c575-3580-4897-95fb-83f45d7435ae
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0172
'type1'과 'type2'는 서로 암시적으로 변환되므로 조건식의 형식을 확인할 수 없습니다.  
  
 조건문에서 `:` 연산자의 한쪽에 있는 형식을 변환할 수 있어야 합니다. 또한 상호 변환 루틴이 없어야 합니다. 하나의 변환만 필요합니다. 자세한 내용은 [변환 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/conversion-operators)을 참조하세요.  
  
 다음 샘플에서는 CS0172를 생성합니다.  
  
```  
// CS0172.cs public class Square { public class Circle { public static implicit operator Circle(Square aa) { return null; } public static implicit operator Square(Circle aa) // using explicit resolves this error // public static explicit operator Square(Circle aa) { return null; } } public static void Main() { Circle aa = new Circle(); Square ii = new Square(); object o = (1 == 1) ? aa : ii;   // CS0172 // the following cast would resolve this error // (1 == 1) ? aa : (Circle)ii; } }  
```