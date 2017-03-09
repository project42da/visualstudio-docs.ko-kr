---
title: "컴파일러 오류 CS1732 | Microsoft Docs"
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
  - "CS1732"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1732"
ms.assetid: 72c7f7fc-d5f2-4538-9b02-50dda54d3b1e
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1732
매개 변수가 필요합니다.  
  
 이 오류는 람다 식에서 입력 매개 변수 뒤에 쉼표가 있지만 다음 매개 변수를 지정하지 않는 경우에 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  쉼표를 제거하거나, 컴파일러에 필요한 입력 매개 변수를 쉼표 뒤에 추가합니다.  
  
## 예제  
 다음 예제에서는 CS1732를 생성합니다.  
  
```  
// cs1732.cs // compile with: /target:library class Test { delegate void D(int x, int y); static void Main() { D d = (x,) => { }; // CS1732 } }  
```