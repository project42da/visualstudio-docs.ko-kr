---
title: "컴파일러 오류 CS0623 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0623"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0623"
ms.assetid: c9fd6888-b9c5-48bf-b25b-2fae1446ad24
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0623
배열 이니셜라이저는 변수 또는 필드 이니셜라이저에서만 사용할 수 있습니다. 대신 새 식을 사용해 봅니다.  
  
 허용되지 않는 컨텍스트에서 배열 이니셜라이저를 사용하여 배열을 초기화하려고 했습니다.  
  
## 예제  
 다음 예제에서는 컴파일러가 \\{4\\}를 외부 배열 이니셜라이저 내에 포함된 배열 이니셜라이저로 해석하기 때문에 CS0623을 생성합니다.  
  
```  
//cs0632.cs using System; class X { public int[] x = { 2, 3, {4}}; //CS0623 }  
```  
  
## 참고 항목  
 [배열](/dotnet/csharp/programming-guide/arrays/index)