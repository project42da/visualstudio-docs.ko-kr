---
title: "컴파일러 오류 CS0471 | Microsoft Docs"
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
  - "CS0471"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0471"
ms.assetid: 3b666461-c57b-45f4-83d3-a23786e29ae9
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0471
'name' 메서드는 제네릭 메서드가 아닙니다. 식 목록을 사용하려면 \< 식 주위에 괄호를 사용하세요.  
  
 이 오류는 코드에 괄호 없이 식 목록이 포함된 경우에 생성됩니다.  
  
## 예제  
 다음 예제에서는 CS0471을 생성합니다.  
  
```  
// CS0471.cs // compile with: /t:library class Test { public void F(bool x, bool y) {} public void F1() { int a = 1, b = 2, c = 3; F(a<b, c>(3));    // CS0471 // To resolve, try the following instead: // F((a<b), c>(3)); } }  
  
```