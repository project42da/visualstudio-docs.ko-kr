---
title: "컴파일러 오류 CS0276 | Microsoft Docs"
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
  - "CS0276"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0276"
ms.assetid: 0c49017f-c7a9-42a5-9d0a-6f1d82142bd7
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0276
'property\/indexer': 접근자의 접근성 한정자는 속성 또는 인덱서에 get 접근자와 set 접근자가 모두 있는 경우에만 사용할 수 있습니다.  
  
 이 오류는 한 접근자에서만 속성 또는 인덱서를 선언하고 해당 접근자에 액세스 한정자를 사용하는 경우에 발생합니다. 이 문제를 해결하려면 액세스 한정자를 제거하거나 다른 접근자를 추가합니다.  
  
## 예제  
 다음 예제에서는 CS0276을 생성합니다.  
  
```  
// CS0276.cs public class MyClass { public int Property { protected set { }   // CS0276 } public int Property2 { internal get { }   // CS0276 } }  
```