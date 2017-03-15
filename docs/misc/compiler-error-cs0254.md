---
title: "컴파일러 오류 CS0254 | Microsoft Docs"
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
  - "CS0254"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0254"
ms.assetid: 85b2ab1e-0011-4f1d-9181-76b9c9f3d914
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0254
fixed 문의 오른쪽에는 캐스트 식을 할당할 수 없습니다.  
  
 [fixed](/dotnet/csharp/language-reference/keywords/fixed-statement) 식의 오른쪽에서는 캐스트를 사용할 수 없습니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
 다음 샘플에서는 CS0254를 생성합니다.  
  
```  
// CS0254.cs // compile with: /unsafe class Point { public uint x, y; } class FixedTest { unsafe static void SquarePtrParam (int* p) { *p *= *p; } unsafe public static void Main() { Point pt = new Point(); pt.x = 5; pt.y = 6; fixed (int* p = (int*)&pt.x)   // CS0254 // try the following line instead // fixed (uint* p = &pt.x) { SquarePtrParam ((int*)p); } } }  
```