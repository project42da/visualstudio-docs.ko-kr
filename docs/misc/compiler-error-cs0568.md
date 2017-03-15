---
title: "컴파일러 오류 CS0568 | Microsoft Docs"
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
  - "CS0568"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0568"
ms.assetid: dc9e1263-f58d-4c95-9165-27ba7757bc7b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0568
구조체는 매개 변수가 없는 명시적 생성자를 포함할 수 없습니다.  
  
 각 [struct](/dotnet/csharp/language-reference/keywords/struct)에 이미 개체를 0으로 초기화하는 기본 생성자가 있습니다. 따라서 구조체에 대해 만들 수 있는 생성자는 하나 이상의 매개 변수를 사용해야 합니다.  
  
 다음 샘플에서는 CS0568을 생성합니다.  
  
```  
// CS0568.cs public struct ClassY { public int field1; public ClassY(){}   // CS0568, cannot have no param constructor // Try following instead: // public ClassY(int i) // { //    field1 = i; // } } public class ClassX { public static void Main() { } }  
```