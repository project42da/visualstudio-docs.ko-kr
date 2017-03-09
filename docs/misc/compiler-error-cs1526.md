---
title: "컴파일러 오류 CS1526 | Microsoft Docs"
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
  - "CS1526"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1526"
ms.assetid: 92feeb9f-e577-4c08-b12b-c19822857200
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1526
new 식은 형식 뒤에 \(\), \[\] 또는 {}가 필요합니다.  
  
 개체에 대한 메모리를 동적으로 할당하는 데 사용하는 [new](/dotnet/csharp/language-reference/keywords/new) 연산자를 올바르게 지정하지 않았습니다.  
  
## 예제  
 다음 샘플은 `new`를 사용하여 배열 및 개체에 대한 공간을 할당하는 방법을 보여 줍니다.  
  
```  
// CS1526.cs public class y { public static int i = 0; public int myi = 0; } public class z { public static void Main() { y py = new y;   // CS1526 y[] aoys = new y[10];   // Array of Ys for (int i = 0; i < aoys.Length; i++) aoys[i] = new y();   // an object of type y } }  
```