---
title: "컴파일러 오류 CS0456 | Microsoft Docs"
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
  - "CS0456"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0456"
ms.assetid: d714ec06-a7f4-405e-bf32-423696848319
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0456
형식 매개 변수 'Type Parameter Name 1'에 'struct' 제약 조건이 있으므로 'Type Parameter Name 1'은 'Type Parameter Name 2'에 대한 제약 조건으로 사용할 수 없습니다.  
  
 이러한 제약 조건을 두 번째 형식 매개 변수에서 제약 조건으로 사용할 수 없도록 값 형식 제약 조건이 암시적으로 봉인됩니다. 이는 값 형식을 재정의할 수 없기 때문입니다. 이 오류를 해결하려면 첫 번째 형식 매개 변수를 사용하여 간접적으로 수행하는 대신 두 번째 형식 매개 변수에 직접 값 형식 제약 조건을 저장합니다.  
  
## 예제  
 다음 샘플에서는 CS0456을 생성합니다.  
  
```  
// CS0456.cs // compile with: /target:library public class GenericsErrors { public class G5<T> where T : struct { public class N<U> where U : T {}   // CS0456 public class N2<U> where U : struct {}   // OK } }  
```