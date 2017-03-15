---
title: "컴파일러 오류 CS0470 | Microsoft Docs"
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
  - "CS0470"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0470"
ms.assetid: b5a8e820-aa5c-4f69-b5c6-01c6a6bb82d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0470
'method' 메서드는 'type' 형식에 대한 'accessor' 인터페이스 접근자를 구현할 수 없습니다. 명시적 인터페이스 구현을 사용합니다.  
  
 이 오류는 접근자가 인터페이스를 구현하려고 할 때 발생합니다. 명시적 인터페이스 구현을 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0470을 생성합니다.  
  
```  
// CS0470.cs // compile with: /target:library interface I { int P { get; } } class MyClass : I { public int get_P() { return 0; }   // CS0470 public int P2 { get { return 0;} }   // OK }  
  
```