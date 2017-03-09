---
title: "컴파일러 경고(수준 2) CS0458 | Microsoft Docs"
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
  - "CS0458"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0458"
ms.assetid: 0986c620-b4bc-4e4b-976f-88359cfa3a45
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0458
식의 결과 값은 항상 'type name' 형식의 'null'입니다.  
  
 이 경고는 항상 결과가 `null`인 `nullable` 식에 의해 발생합니다.  
  
 다음 코드는 CS0458 경고를 생성합니다.  
  
## 예제  
 이 예제에서는 이 오류를 발생시키는 다양한 `nullable` 형식 작업을 보여 줍니다.  
  
```  
// CS0458.cs using System; public  class Test { public static void Main() { int a = 5; int? b = a + null;    // CS0458 int? qa = 15; b = qa + null;        // CS0458 b -= null;            // CS0458 int? qa2 = null; b = qa2 + null;       // CS0458 qa2 -= null;          // CS0458 } }  
```