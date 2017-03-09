---
title: "컴파일러 오류 CS0506 | Microsoft Docs"
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
  - "CS0506"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0506"
ms.assetid: 1286957c-2505-4b5f-ade0-154ad5f09dc1
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0506
'function1': 상속된 'function2' 멤버는 "virtual", "abstract" 또는 "override"로 표시되지 않았으므로 재정의할 수 없습니다.  
  
 **virtual**, **abstract** 또는 `override`로 명시적으로 표시되지 않은 메서드를 재정의했습니다.  
  
 다음 샘플에서는 CS0506을 생성합니다.  
  
```  
// CS0506.cs namespace MyNameSpace { abstract public class ClassX { public int i = 0; public int f() { return 0; } // Try the following definition for f() instead: // abstract public int f(); } public class ClassY : ClassX { public override int f()   // CS0506 { return 0; } public static int Main() { return 0; } } }  
```