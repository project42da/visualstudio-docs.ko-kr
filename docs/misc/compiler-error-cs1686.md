---
title: "컴파일러 오류 CS1686 | Microsoft Docs"
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
  - "CS1686"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1686"
ms.assetid: 46a9e82b-57f4-416d-8e49-242bfff5433a
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1686
지역 'variable' 또는 해당 멤버의 주소를 가져와 무명 메서드 또는 람다 식 안에 사용할 수 없습니다.  
  
 이 오류는 변수를 사용하고 해당 주소를 사용하려고 하며 무명 메서드 내에서 이러한 작업 중 하나를 수행하는 경우에 생성됩니다.  
  
## 예제  
 다음 샘플에서는 CS1686을 생성합니다.  
  
```  
// CS1686.cs // compile with: /unsafe /target:library class MyClass { public unsafe delegate int * MyDelegate(); public unsafe int * Test() { int j = 0; MyDelegate d = delegate { return &j; };   // CS1686 return &j;   // OK } }  
```