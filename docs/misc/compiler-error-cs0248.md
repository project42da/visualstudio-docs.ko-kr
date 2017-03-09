---
title: "컴파일러 오류 CS0248 | Microsoft Docs"
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
  - "CS0248"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0248"
ms.assetid: a7ddfd26-a836-47b8-b432-53876e06da31
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0248
음수 크기의 배열은 만들 수 없습니다.  
  
 배열 크기가 음수로 지정되었습니다. 자세한 내용은 [배열](/dotnet/csharp/programming-guide/arrays/index)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0248을 생성합니다.  
  
```  
// CS0248.cs class MyClass { public static void Main() { int[] myArray = new int[-3] {1,2,3};   // CS0248, pass a nonnegative number } }  
```