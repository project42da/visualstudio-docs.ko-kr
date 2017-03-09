---
title: "&#39;ReadOnly&#39; 속성에는 &#39;Get&#39;에 대한 액세스 한정자를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31105"
  - "bc31105"
helpviewer_keywords: 
  - "BC31105"
ms.assetid: 54066d8e-eb22-4b99-bb18-45afe61d3b33
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 속성에는 &#39;Get&#39;에 대한 액세스 한정자를 사용할 수 없습니다.
`ReadOnly` 속성 선언은 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement) 및 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 모두에서 액세스 수준을 지정합니다.  
  
 언제든지 속성에 대한 액세스 수준을 지정할 수 있습니다. 또한 속성의 액세스 수준보다 더 제한적인 경우 해당 속성 프로시저\(`Get` 또는 `Set`\) 중 최대 하나에 대해 다른 액세스 수준을 지정할 수 있습니다. 두 속성 프로시저 모두에 대해 액세스 수준을 지정할 수는 없습니다.  
  
 **오류 ID:** BC31105  
  
### 이 오류를 해결하려면  
  
-   `Get` 문에서 액세스 한정자를 제거합니다. 전체 `ReadOnly` 속성을 나타내며 속성에 대해 두 개의 액세스 수준을 사용할 수 없습니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)