---
title: "&#39;&lt;operator&gt;&#39; 연산자에는 두 개의 매개 변수만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc33015"
  - "vbc33015"
helpviewer_keywords: 
  - "BC33015"
ms.assetid: 506ea996-8abe-4dbe-aff4-d3910bf4399e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39; 연산자에는 두 개의 매개 변수만 사용할 수 있습니다.
이항 연산자가 두 개보다 적거나 두 개보다 많은 매개 변수로 정의되었습니다.  
  
 이항 연산자에는 두 개의 매개 변수만 사용할 수 있습니다.  
  
 **오류 ID:** BC33015  
  
### 이 오류를 해결하려면  
  
-   정확히 두 개의 매개 변수를 지정하도록 정의를 조정합니다.  
  
-   하나의 매개 변수가 필요한 경우 단항 연산자를 정의해야 합니다.  
  
-   매개 변수가 필요하지 않거나 두 개 이상 필요한 경우 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)을 사용하여 연산자 대신 `Function` 프로시저를 정의합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)