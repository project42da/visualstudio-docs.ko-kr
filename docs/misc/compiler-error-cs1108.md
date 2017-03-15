---
title: "컴파일러 오류 CS1108 | Microsoft Docs"
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
  - "CS1108"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1108"
ms.assetid: 26e82d6a-6ebf-4beb-912e-1bcb86b668aa
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1108
지정된 한정자를 매개 변수에 모두 사용할 수 없습니다. 매개 변수에 한정자가 너무 많습니다.  
  
 `ref` 및 `out`과 같은 매개 변수 한정자의 특정 조합은 컴파일러에 대해 함께 사용하지 않는 의미가 있기 때문에 허용되지 않습니다.  
  
## 예제  
 다음 예제에서는 CS1108을 생성합니다.  
  
```  
// cs1108.cs // Compile with: /target:library public class Test { // Regular Instance Method. public void TestMethod(ref out int i) {} // CS1108 }  
```