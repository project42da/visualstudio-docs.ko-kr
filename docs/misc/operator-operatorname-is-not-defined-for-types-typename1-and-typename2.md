---
title: "&#39;&lt;typename1&gt;&#39; 및 &#39;&lt;typename2&gt;&#39; 형식에 대한 &#39;&lt;operatorname&gt;&#39; 연산자가 정의되지 않았습니다. | Microsoft Docs"
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
  - "vbc31080"
  - "bc31080"
helpviewer_keywords: 
  - "BC31080"
ms.assetid: d2f77450-2bf2-4b1e-b95f-dbc7878f2777
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename1&gt;&#39; 및 &#39;&lt;typename2&gt;&#39; 형식에 대한 &#39;&lt;operatorname&gt;&#39; 연산자가 정의되지 않았습니다.
'\<typename1\>' 및 '\<typename2\>' 형식에 대한 '\<operatorname\>' 연산자가 정의되지 않았습니다. 두 참조 형식을 비교하려면 'Is' 연산자를 사용하세요.  
  
 지정된 형식에 적합하지 않은 방식으로 연산자를 사용하려고 했습니다. 이 오류는 `Is` 연산자 대신 "\=" 연산자를 사용하여 두 개체를 비교하는 경우에 발생할 수 있습니다.  
  
 **오류 ID:** BC31080  
  
### 이 오류를 해결하려면  
  
1.  `Is` 연산자를 사용하여 두 참조 형식을 비교합니다.  
  
2.  `Is` 연산자와 함께 `Not` 연산자를 사용하여 같지 않음을 나타냅니다. 예:  
  
     [!code-vb[VbVbalrOOP#89](../misc/codesnippet/VisualBasic/operator-operatorname-is-not-defined-for-types-typename1-and-typename2_1.vb)]  
  
## 참고 항목  
 [Is Operator](/dotnet/visual-basic/language-reference/operators/is-operator)   
 [\= Operator](/dotnet/visual-basic/language-reference/operators/assignment-operator)   
 [Not Operator](/dotnet/visual-basic/language-reference/operators/not-operator)