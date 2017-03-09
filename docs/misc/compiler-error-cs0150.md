---
title: "컴파일러 오류 CS0150 | Microsoft Docs"
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
  - "CS0150"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0150"
ms.assetid: 1fd08ca5-e1a9-42f5-93de-2916a3bdcad1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0150
상수 값이 필요합니다.  
  
 상수가 필요한 변수가 있습니다. 자세한 내용은 [switch](/dotnet/csharp/language-reference/keywords/switch)을 참조하세요.  
  
 다음 샘플에서는 CS0150을 생성합니다.  
  
```  
// CS0150.cs namespace MyNamespace { public class MyClass { public static void Main() { int i = 0; int j = 0; switch(i) { case j:   // CS0150, j is a variable int, not a constant int // try the following line instead // case 1: } } } }  
```  
  
 이 오류는 배열 크기가 변수 값으로 지정되고 배열 이니셜라이저로 초기화되는 경우에도 생성됩니다. 오류를 제거하려면 별도 문에서 배열을 초기화합니다.  
  
```  
// CS0150.cs namespace MyNamespace { public class MyClass { public static void Main() { int size = 2; double[] nums = new double[size] { 46.9, 89.4 }; //CS0150 // Try the following lines instead // double[] nums = new double[size]; // nums[0] = 46.9; // nums[1] = 89.4; } } }  
  
```