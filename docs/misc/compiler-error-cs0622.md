---
title: "컴파일러 오류 CS0622 | Microsoft Docs"
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
  - "CS0622"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0622"
ms.assetid: aef77a69-d8b7-41f8-9539-258deaef5cc4
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0622
배열 이니셜라이저 식은 배열 형식에 할당하는 데에만 사용할 수 있습니다. 대신 새 식을 사용해 봅니다.  
  
 배열을 초기화하는 데 적합한 구문이 배열이 아닌 선언에 사용되었습니다.  
  
## 예제  
 다음 샘플에서는 CS0622를 생성합니다.  
  
```  
// CS0622.cs using System; public class Test { public static void Main () { Test t = { new Test() };   // CS0622 // Try the following instead: // Test[] t = { new Test() }; } }  
```