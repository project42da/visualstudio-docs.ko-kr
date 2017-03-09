---
title: "컴파일러 경고(수준 3) CS1717 | Microsoft Docs"
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
  - "CS1717"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1717"
ms.assetid: 5b150a2c-5d61-4cd8-b4d4-e6c2b93b52c6
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS1717
같은 변수에 할당했습니다. 다른 요소를 할당하시겠습니까?  
  
 이 경고는 변수를 `a = a`과 같이 자신에게 할당할 때 발생합니다.  
  
 다음과 같은 몇 가지 일반적인 실수로 인해 이 경고가 생성될 수 있습니다.  
  
-   `if (a = a)`과 같은 **if** 문의 조건으로 `a = a`을 씁니다. 원래 의도는 항상 true인 `if (a == a)`이므로 이를 `if (true)`처럼 더 간결하게 쓸 수 있습니다.  
  
-   잘못 입력합니다. 원래 의도는 `a = b`입니다.  
  
-   매개 변수가 필드와 동일한 이름을 가진 생성자에서 **this** 키워드를 사용하지 않습니다. 원래 의도는 `this.a = a`입니다.  
  
## 예제  
 다음 샘플에서는 CS1717을 생성합니다.  
  
```  
// CS1717.cs // compile with: /W:3 public class Test { public static void Main() { int x = 0; x = x;   // CS1717 } }  
```