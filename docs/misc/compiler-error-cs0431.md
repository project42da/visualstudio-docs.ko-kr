---
title: "컴파일러 오류 CS0431 | Microsoft Docs"
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
  - "CS0431"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0431"
ms.assetid: 05da7ea7-f33d-48d4-948e-d64be56f91ba
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0431
'identifier' 별칭은 형식을 참조하므로 '::'과 함께 사용할 수 없습니다. 대신 '.'를 사용하세요.  
  
 형식을 참조하는 별칭과 함께 "::"을 사용했습니다. 이 오류를 해결하려면 "." 연산자를 사용합니다.  
  
 다음 샘플에서는 CS0431을 생성합니다.  
  
```  
// CS0431.cs using A = Outer; public class Outer { public class Inner { public static void Meth() {} } } public class MyClass { public static void Main() { A::Inner.Meth();   // CS0431 A.Inner.Meth();   // OK } }  
```