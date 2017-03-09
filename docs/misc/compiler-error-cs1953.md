---
title: "컴파일러 오류 CS1953 | Microsoft Docs"
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
  - "CS1953"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1953"
ms.assetid: b8af5eed-0f3b-4258-b4e2-f5d184288239
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1953
람다 식 트리에는 메서드 그룹을 사용할 수 없습니다.  
  
 메서드 호출에 `()` 연산자가 필요합니다. 이 연산자가 없는 메서드 이름은 해당 이름을 가진 오버로드된 모든 메서드 집합인 메서드 그룹을 참조합니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드를 호출하려면 `()` 연산자를 추가합니다.  
  
## 예제  
 다음 예제에서는 CS1953을 생성합니다.  
  
```  
// cs1953.cs using System; using System.Linq.Expressions; class CS1953 { public static void Main() { double num = 10; Expression<Func<bool>> testExpr = () => num.GetType is int; // CS1953 } }  
```