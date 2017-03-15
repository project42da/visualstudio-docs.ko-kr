---
title: "컴파일러 오류 CS1628 | Microsoft Docs"
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
  - "CS1628"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1628"
ms.assetid: 520f864c-afe3-4db2-b44e-cfaac28ff49d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1628
무명 메서드, 람다 식 또는 쿼리 식 안에서는 ref 또는 out 매개 변수 'parameter'를 사용할 수 없습니다.  
  
 이 오류는 무명 메서드 블록 내에서 ref 또는 out 매개 변수를 사용한 경우 발생합니다. 이 오류를 방지하려면 지역 변수 또는 일부 다른 생성자를 사용합니다.  
  
 다음 샘플에서는 CS1628을 생성합니다.  
  
```  
// CS1628.cs delegate int MyDelegate(); class C { public static void F(ref int i) { MyDelegate d = delegate { return i; };  // CS1628 // Try this instead: // int tmp = i; // MyDelegate d = delegate { return tmp; }; } public static void Main() { } }  
```