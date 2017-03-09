---
title: "컴파일러 오류 CS1649 | Microsoft Docs"
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
  - "CS1649"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1649"
ms.assetid: 6355c7f2-157c-441d-8925-500062988636
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1649
읽기 전용 필드 'identifier'의 멤버에는 ref 또는 out을 전달할 수 없습니다. 단 생성자에서는 예외입니다.  
  
 이 오류는 `readonly` 필드의 멤버인 함수에 변수를 `ref` 또는 `out` 인수로 전달하는 경우에 발생합니다.`ref` 및 `out` 매개 변수를 수정할 수 있기 때문에 이 작업은 허용되지 않습니다. 이 오류를 해결하려면 필드의 `readonly` 키워드를 제거하거나 `readonly` 필드의 멤버를 함수에 전달하지 마세요. 예를 들어 다음 예제와 같이 수정할 수 있는 임시 변수를 만들고 임시 변수를 `ref` 인수로 전달할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 CS1649를 생성합니다.  
  
```  
// CS1649.cs public struct Inner { public int i; } class Outer { public readonly Inner inner = new Inner(); } class D { static void f(ref int iref) { } static void Main() { Outer outer = new Outer(); f(ref outer.inner.i);  // CS1649 // Try this code instead: // int tmp = outer.inner.i; // f(ref tmp); } }  
```