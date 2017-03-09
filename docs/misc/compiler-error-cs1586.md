---
title: "컴파일러 오류 CS1586 | Microsoft Docs"
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
  - "CS1586"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1586"
ms.assetid: 408a4495-6fe6-4e95-a49f-a4d041675fff
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1586
배열을 만들 때에는 배열 크기 또는 배열 이니셜라이저가 있어야 합니다.  
  
 배열이 잘못 선언되었습니다.  
  
 다음 샘플에서는 CS1586을 생성합니다.  
  
```  
// CS1586.cs using System; class MyClass { public static void Main() { int[] a = new int[];   // CS1586 // try the following line instead int[] b = new int[5]; } }  
```  
  
## 참고 항목  
 [배열](/dotnet/csharp/programming-guide/arrays/index)