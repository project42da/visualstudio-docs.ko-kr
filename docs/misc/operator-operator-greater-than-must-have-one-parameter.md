---
title: "&#39;&lt;operator&gt;&#39; 연산자에는 한 개의 매개 변수만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc33014"
  - "vbc33014"
helpviewer_keywords: 
  - "BC33014"
ms.assetid: 512a5724-a6c5-4437-a608-7d6b10e68d49
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39; 연산자에는 한 개의 매개 변수만 사용할 수 있습니다.
단항 연산자는 둘 이상의 매개 변수 또는 매개 변수 없이 정의됩니다.  
  
 단항 연산자에는 한 개의 매개 변수만 사용할 수 있습니다.  
  
 **오류 ID:** BC33014  
  
### 이 오류를 해결하려면  
  
-   정확히 하나의 매개 변수를 지정하도록 정의를 조정합니다.  
  
-   두 개의 매개 변수가 필요한 경우 이항 연산자를 정의해야 합니다.  
  
-   매개 변수가 필요하지 않거나 두 개 이상 필요한 경우 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)을 사용하여 연산자 대신 `Function` 프로시저를 정의합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)