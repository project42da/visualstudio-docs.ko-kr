---
title: "컴파일러 오류 CS0572 | Microsoft Docs"
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
  - "CS0572"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0572"
ms.assetid: ec950e95-13da-41b5-90cd-9e673d62498b
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0572
'type': 식을 통해 형식을 참조할 수 없습니다. 대신 'path\_to\_type'을 시도하세요.  
  
 식별자를 통해 클래스의 멤버에 액세스하려고 했습니다. 이는 이 상황에서는 허용되지 않습니다.  
  
 다음 샘플에서는 CS0572를 생성합니다.  
  
```  
// CS0572.cs using System; class C { public class Inner { public static int v = 9; } } class D : C { public static void Main() { C cValue = new C(); Console.WriteLine(cValue.Inner.v);   // CS0572 // try the following line instead // Console.WriteLine(C.Inner.v); } }  
```