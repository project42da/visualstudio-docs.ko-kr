---
title: "Option Strict On에서는 모든 메서드 매개 변수에 &#39;As&#39; 절을 사용해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30211"
  - "bc30211"
helpviewer_keywords: 
  - "BC30211"
ms.assetid: 855795ce-8499-4525-a1de-cbb8ba364cd7
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 모든 메서드 매개 변수에 &#39;As&#39; 절을 사용해야 합니다.
메서드에 `As` 절이 없는 매개 변수가 포함되어 있습니다.`Option Strict`가 설정된 경우에는 `As` 절을 통해 모든 변수, 속성, 프로시저 인수 및 함수 반환을 선언하여 해당 데이터 형식을 지정해야 합니다\(예: `Sub GetData(ByVal filter As String)`\).  
  
 **오류 ID:** BC30211  
  
### 이 오류를 해결하려면  
  
-   `As` 키워드의 철자가 맞는지 확인합니다.  
  
-   선언된 변수에 대해 `As` 절을 제공하거나 `Option Strict`를 끕니다.  
  
## 참고 항목  
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Sub Statement](/dotnet/visual-basic/language-reference/statements/sub-statement)   
 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)