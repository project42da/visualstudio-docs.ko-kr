---
title: "컴파일러 오류 CS0450 | Microsoft Docs"
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
  - "CS0450"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0450"
ms.assetid: 8eb0e98b-d7a1-49a7-8e55-36e2eb0057ff
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0450
'Type Parameter Name': constraint 클래스와 'class' 또는 'struct' 제약 조건을 둘 다 지정할 수는 없습니다.  
  
 구조체와 클래스는 함께 사용할 수 없는 범주이므로 형식 매개 변수가 구조체 형식 제약 조건에 의해 제한되는 경우 특정 클래스 형식에 의해서도 제한되는 것은 논리적으로 허용되지 않습니다. 형식 매개 변수가 특정 클래스 형식 제약 조건에 의해 제한되는 경우 정의에 따라 클래스 형식 제약 조건에 의해서도 제한되므로 클래스 형식 제약 조건을 별도로 지정하면 중복됩니다.  
  
## 예제  
  
```  
// CS0450.cs // compile with: /t:library public class GenericsErrors { public class B { } public class G3<T> where T : struct, B { } // CS0450 // To resolve, use the following line instead: // public class G3<T> where T : B { } }  
```