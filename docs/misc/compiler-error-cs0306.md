---
title: "컴파일러 오류 CS0306 | Microsoft Docs"
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
  - "CS0306"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0306"
ms.assetid: f340a3ce-6140-4001-bb00-628a2985ddd6
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0306
'type' 형식은 형식 인수로 사용할 수 없습니다.  
  
 형식 매개 변수로 사용되는 형식이 허용되지 않습니다. 이는 형식이 포인터 형식이기 때문일 수 있습니다.  
  
 다음 예제에서는 CS0306을 생성합니다.  
  
```  
// CS0306.cs class C<T> { } class M { // CS0306 – int* not allowed as a type parameter C<int*> f; }  
```