---
title: "컴파일러 오류 CS1733 | Microsoft Docs"
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
  - "CS1733"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1733"
ms.assetid: 2188aabe-404d-4a95-a11a-736dbd848508
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1733
식이 필요합니다.  
  
 이 오류는 오류가 발생한 줄에서 컴파일러가 식을 예상하고 있을 때 생성됩니다. 다음 예제에서 이니셜라이저의 후행 쉼표는 뒤에 다른 식이 따라온다는 것을 컴파일러에게 나타냅니다.  
  
### 이 오류를 해결하려면  
  
-   누락된 식을 제공합니다.  
  
-   컴파일러에게 식을 기대하게 만드는 토큰을 제거합니다.  
  
## 예제  
 다음 예제는 후행 쉼표로 인해 CS1733을 생성합니다.  
  
```  
// cs1733.cs using System.Collections.Generic; public class Test { public static void Main() { List<int> list = new List<int>() {{ 1, 2, }};// CS1733 } }  
```