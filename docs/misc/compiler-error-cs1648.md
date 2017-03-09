---
title: "컴파일러 오류 CS1648 | Microsoft Docs"
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
  - "CS1648"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1648"
ms.assetid: 5cf1bc84-cd18-4df2-942f-1cc17eabacd6
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1648
읽기 전용 필드 'identifier'의 멤버는 수정할 수 없습니다. 단 생성자 또는 변수 이니셜라이저에서는 예외입니다.  
  
 이 오류는 수정할 수 없는 읽기 전용 필드의 멤버를 수정하려고 시도할 때 발생합니다. 이 오류를 해결하려면 읽기 전용 필드에 대한 할당을 생성자 또는 변수 이니셜라이저로 제한하거나 필드의 선언에서 읽기 전용 키워드를 제거합니다.  
  
 다음 샘플에서는 CS1648을 생성합니다.  
  
```  
// CS1648.cs public struct Inner { public int i; } class Outer { public readonly Inner inner = new Inner(); } class D { static void Main() { Outer outer = new Outer(); outer.inner.i = 1;  // CS1648 } }  
```