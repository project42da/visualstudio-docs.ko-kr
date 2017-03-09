---
title: "컴파일러 오류 CS0226 | Microsoft Docs"
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
  - "CS0226"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0226"
ms.assetid: 9f8c74c4-de21-41fb-84e1-ef32a4b23ced
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0226
\_\_arglist 식은 call 또는 new 식 내부에만 있어야 합니다.  
  
 지원되지 않는 키워드 `__arglist`는 메서드 호출 또는 새 식에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 CS0226을 생성합니다.  
  
```  
// cs0226.cs using System; public class C { public static int Main () { __arglist(1,"This is a string"); // CS0226 return 0; } }  
```