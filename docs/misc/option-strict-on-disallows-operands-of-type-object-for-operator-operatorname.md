---
title: "Option Strict On에서는 &#39;&lt;operatorname&gt;&#39; 연산자에 대해 Object 형식의 피연산자를 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32013"
  - "vbc32013"
helpviewer_keywords: 
  - "BC32013"
ms.assetid: cd197da8-2676-453b-884b-3231fb6f909d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;operatorname&gt;&#39; 연산자에 대해 Object 형식의 피연산자를 사용할 수 없습니다.
Option Strict On에서는 '\<operatorname\>' 연산자에 대해 Object 형식의 피연산자를 사용할 수 없습니다. Is 연산자를 사용하여 개체 ID를 테스트합니다.  
  
 `Option Strict`가 `On`인 경우 `=`와 같은 산술 비교 연산자가 하나 이상의 개체 변수와 함께 사용됩니다.  
  
 **오류 ID:** BC32013  
  
### 이 오류를 해결하려면  
  
1.  개체 변수에 숫자 값이 포함되어 있고 산술 비교하려는 경우 `Option Strict Off`를 해제합니다.  
  
2.  `Is` 연산자를 사용하여 개체 ID를 비교합니다.  
  
## 참고 항목  
 [Comparison Operators](/dotnet/visual-basic/language-reference/operators/comparison-operators)   
 [Is Operator](/dotnet/visual-basic/language-reference/operators/is-operator)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)