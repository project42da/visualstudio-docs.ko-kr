---
title: "컴파일러 오류 CS0283 | Microsoft Docs"
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
  - "CS0283"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0283"
ms.assetid: f94a5b84-92c5-4602-894d-6f856d57e0e6
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0283
'type' 형식은 const로 선언할 수 없습니다.  
  
 상수 선언에서 지정된 형식은 `byte`, `char`, `short`, `int`, `long`, `float`, `double`, `decimal`, `bool`, `string`, enum\-type 또는 null 값이 할당된 참조 형식이어야 합니다. 각 상수 식은 대상 형식 또는 암시적 변환에서 대상 유형으로 변환될 수 있는 형식의 값을 제공해야 합니다.  
  
## 예제  
 다음 예제에서는 CS0283을 생성합니다.  
  
```  
// CS0283.cs struct MyTest { } class MyClass { // To resolve the error but retain the "const-ness", // change const to readonly. const MyTest test = new MyTest();   // CS0283 public static int Main() { return 1; } }  
```