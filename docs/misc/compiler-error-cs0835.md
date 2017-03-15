---
title: "컴파일러 오류 CS0835 | Microsoft Docs"
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
  - "CS0835"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0835"
ms.assetid: 593c26f6-6d82-49a6-8ace-4d29dd9f5fbe
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0835
람다 식을 형식 인수 'type'이 대리자 형식이 아닌 식 트리로 변환할 수 없습니다.  
  
 람다 식이 식 트리로 변환되면 식 트리에 해당 인수에 대한 대리자 형식이 있어야 합니다. 또한 람다 식이 대리자 형식으로 변환 가능해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  형식 매개 변수를 `int`에서 대리자 형식으로 변경합니다\(예: `Func<int,int>`\).  
  
## 예제  
 다음 예제에서는 CS0835를 생성합니다.  
  
```  
// cs0835.cs using System; using System.Linq; using System.Linq.Expressions; public class C { public static int Main() { Expression<int> e = x => x + 1; // CS0835 // Try the following line instead. // Expression<Func<int,int>> e2 = x => x + 1; return 1; } }  
```