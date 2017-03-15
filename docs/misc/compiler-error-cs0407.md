---
title: "컴파일러 오류 CS0407 | Microsoft Docs"
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
  - "CS0407"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0407"
ms.assetid: 59112fb9-4641-466e-b738-b3228539a09e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0407
'return\-type method'의 반환 형식이 잘못되었습니다.  
  
 메서드가 대리자 형식과 호환되지 않습니다. 인수 형식은 일치하지만 반환 형식이 해당 대리자의 올바른 반환 형식이 아닙니다. 이 오류를 방지하려면 다른 메서드를 사용하여 메서드의 반환 형식을 변경하거나 대리자의 반환 형식을 변경합니다.  
  
## 예제  
 다음 샘플에서는 CS0407을 생성합니다.  
  
```  
// CS0407.cs public delegate int MyDelegate(); class C { MyDelegate d; public C() { d = new MyDelegate(F);  // OK: F returns int d = new MyDelegate(G);  // CS0407 – G doesn't return int } public int F() { return 1; } public void G() { } public static void Main() { C c1 = new C(); } }  
```