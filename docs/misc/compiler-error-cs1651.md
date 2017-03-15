---
title: "컴파일러 오류 CS1651 | Microsoft Docs"
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
  - "CS1651"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1651"
ms.assetid: ce1043e3-b453-4b4c-b949-f344834e3845
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1651
정적 읽기 전용 필드 'identifier'의 필드는 ref 또는 out으로 전달할 수 없습니다. 단 정적 생성자에서는 예외입니다.  
  
 이 오류는 정적 읽기 전용 필드의 멤버인 함수에 변수를 ref 인수로 전달하는 경우에 발생합니다. 함수에서 ref 매개 변수를 수정할 수 있기 때문에 이 작업은 허용되지 않습니다. 이 오류를 해결하려면 필드의 **readonly** 키워드를 제거하거나 읽기 전용 필드의 멤버를 함수에 전달하지 마세요. 예를 들어 다음 예제와 같이 수정할 수 있는 임시 변수를 만들고 임시 변수를 ref 인수로 전달할 수 있습니다.  
  
 다음 샘플에서는 CS1651을 생성합니다.  
  
```  
// CS1651.cs public struct Inner { public int i; } class Outer { public static readonly Inner inner = new Inner(); } class D { static void f(ref int iref) { } static void Main() { f(ref Outer.inner.i);  // CS1651 // Try this instead: // int tmp = Outer.inner.i; // f(ref tmp); } }  
```