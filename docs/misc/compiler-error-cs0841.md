---
title: "컴파일러 오류 CS0841 | Microsoft Docs"
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
  - "CS0841"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0841"
ms.assetid: eb67c244-a930-4291-ae2a-5832e8916ed7
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0841
'name' 변수는 선언되지 않으면 사용할 수 없습니다.  
  
 변수는 사용하기 전에 선언되어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  오류가 발생하는 줄 앞으로 변수 선언을 이동합니다.  
  
## 예제  
 다음 예제에서는 CS0841을 생성합니다.  
  
```  
// cs0841.cs using System; public class C { public static int Main() { j = 5; // CS0841 int j; // To fix, move this line up. return 1; } }  
```