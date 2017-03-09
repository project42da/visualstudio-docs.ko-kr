---
title: "Option Strict On에서는 모든 변수 선언에 &#39;As&#39; 절을 사용해야 합니다. | Microsoft Docs"
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
  - "bc30209"
  - "vbc30209"
helpviewer_keywords: 
  - "BC30209"
ms.assetid: 69c2e32a-86aa-4075-a142-440605a7063a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 모든 변수 선언에 &#39;As&#39; 절을 사용해야 합니다.
선언이 `As` 절 없이 선언된 변수를 포함합니다.`Option Strict`가 `On`이면 `As` 절을 통해 모든 변수, 속성, 프로시저 인수 및 함수 반환을 선언하여 해당 데이터 형식을 지정해야 합니다\(예: `Dim MyNum As Short`\).  
  
 **오류 ID:** BC30209  
  
### 이 오류를 해결하려면  
  
1.  `As` 키워드의 철자가 맞는지 확인합니다.  
  
2.  선언된 변수에 대해 `As` 절을 제공하거나 `Option Strict Off`를 켭니다.  
  
## 참고 항목  
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [변수 선언](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)