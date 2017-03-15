---
title: "&#39;Exit Operator&#39;가 잘못되었습니다. 연산자를 종료하려면 &#39;Return&#39;을 사용하세요. | Microsoft Docs"
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
  - "bc33008"
  - "vbc33008"
helpviewer_keywords: 
  - "BC33008"
ms.assetid: 8c44456b-8fd2-4168-ad8c-b6da129242ba
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Operator&#39;가 잘못되었습니다. 연산자를 종료하려면 &#39;Return&#39;을 사용하세요.
`Exit Operator` 문이 `Operator` 프로시저에 나타납니다.  
  
 [Return Statement](/dotnet/visual-basic/language-reference/statements/return-statement)을 사용하여 `Operator` 프로시저에서 반환해야 합니다.[Exit Statement](/dotnet/visual-basic/language-reference/statements/exit-statement)은 `Operator` 키워드를 사용하지 않으며 `End Operator` 문은 호출 코드로 제어권을 반환하지 않습니다.  
  
 **오류 ID:** BC33008  
  
### 이 오류를 해결하려면  
  
-   `Exit Operator` 문을 `Return` 문으로 바꿉니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)