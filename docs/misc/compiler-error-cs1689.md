---
title: "컴파일러 오류 CS1689 | Microsoft Docs"
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
  - "CS1689"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1689"
ms.assetid: 5fa6e845-40ef-4451-81ee-acbe2665527a
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1689
'Attribute Name' 특성은 메서드 또는 특성 클래스에만 사용할 수 있습니다.  
  
 이 오류는 **ConditionalAttribute** 특성에서만 발생합니다. 메시지 상태인 이 특성은 메서드 또는 특성 클래스에만 사용할 수 있습니다. 예를 들어 클래스에 이 특성을 적용하려고 하면 이 오류가 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS1689를 생성합니다.  
  
```  
// CS1689.cs // compile with: /target:library [System.Diagnostics.Conditional("A")]   // CS1689 class MyClass {}  
```