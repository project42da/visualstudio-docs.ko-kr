---
title: "&#39;IsNot&#39;의 피연산자는 참조 형식이어야 하는데 이 피연산자의 값 형식은 &#39;&lt;typename&gt;&#39;입니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31419"
  - "vbc31419"
helpviewer_keywords: 
  - "BC31419"
ms.assetid: c44d2936-8c07-443a-b320-ac2bfbc1e9ec
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;IsNot&#39;의 피연산자는 참조 형식이어야 하는데 이 피연산자의 값 형식은 &#39;&lt;typename&gt;&#39;입니다.
식에서 하나 이상의 값 형식 피연산자가 있는 [IsNot Operator](/dotnet/visual-basic/language-reference/operators/isnot-operator)를 사용합니다.  
  
 `IsNot` 연산자는 두 개체 참조가 서로 다른 개체를 참조하는지 여부를 확인합니다. 참조 형식의 포인터 값을 비교하므로 값 형식에는 의미가 없습니다.  
  
 **오류 ID:** BC31419  
  
### 이 오류를 해결하려면  
  
-   두 값 형식의 값을 비교하려는 경우 `=` 또는 `<>` 비교 연산자를 사용합니다.  
  
-   두 참조 형식의 포인터를 비교하려는 경우 두 피연산자에 대한 개체 참조를 사용해야 합니다.[Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2) 키워드와 같이 참조 변수처럼 동작하는 참조 변수 또는 요소를 사용할 수 있습니다.  
  
## 참고 항목  
 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)   
 [How to: Test Whether Two Objects Are the Same](../Topic/How%20to:%20Test%20Whether%20Two%20Objects%20Are%20the%20Same%20\(Visual%20Basic\).md)