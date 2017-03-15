---
title: "컴파일러 오류 CS0442 | Microsoft Docs"
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
  - "CS0442"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0442"
ms.assetid: a411660d-0db6-4b63-b19e-f4538fc201e5
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0442
'Property': 추상 속성에는 전용 접근자를 사용할 수 없습니다.  
  
 이 오류는 "private" 액세스 한정자를 사용하여 추상 접근자를 수정하는 경우에 발생합니다. 해결하려면 다른 액세스 한정자를 사용하거나 속성을 비추상으로 설정합니다.  
  
## 예제  
 다음 샘플에서는 CS0442를 생성합니다.  
  
```  
// CS0442.cs public abstract class MyClass { public abstract int AbstractProperty { get; private set;   // CS0442 // Try this instead: // set; } }  
```