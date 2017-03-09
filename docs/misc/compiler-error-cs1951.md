---
title: "컴파일러 오류 CS1951 | Microsoft Docs"
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
  - "CS1951"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1951"
ms.assetid: 799ba212-a000-44d9-b7da-a8c00eae63fa
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1951
람다 식 트리에는 out 또는 ref 매개 변수를 사용할 수 없습니다.  
  
 식 트리는 식을 데이터 구조로 나타냅니다. 매개 변수를 참조로 전달하는 경우 필요한 특정 메모리 위치를 나타낼 방법이 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  유일한 옵션은 대리자 정의에서 `ref` 한정자를 제거하고 매개 변수를 값으로 전달하는 것입니다.  
  
## 예제  
 다음 예제에서는 CS1951을 생성합니다.  
  
```  
// cs1951.cs using System.Linq; public delegate int TestDelegate(ref int i); class Test { static void Main() { System.Linq.Expressions.Expression<TestDelegate> tree1 = (ref int x) => x; // CS1951 } }  
```  
  
## 참고 항목  
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)