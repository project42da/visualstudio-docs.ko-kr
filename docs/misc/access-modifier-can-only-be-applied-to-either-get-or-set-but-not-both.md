---
title: "액세스 한정자는 &#39;Get&#39; 또는 &#39;Set&#39; 중 하나에만 적용할 수 있습니다. | Microsoft Docs"
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
  - "bc31101"
  - "vbc31101"
helpviewer_keywords: 
  - "BC31101"
ms.assetid: c2a0580c-ff2f-4cc9-9113-6e540f906eec
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 액세스 한정자는 &#39;Get&#39; 또는 &#39;Set&#39; 중 하나에만 적용할 수 있습니다.
속성 선언은 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement), [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 및 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)에서 액세스 수준을 지정합니다.  
  
 언제든지 속성에 대한 액세스 수준을 지정할 수 있습니다. 또한 속성의 액세스 수준보다 더 제한적인 경우 해당 속성 프로시저\(`Get` 또는 `Set`\) 중 최대 하나에 대해 다른 액세스 수준을 지정할 수 있습니다. 두 속성 프로시저 모두에 대해 액세스 수준을 지정할 수는 없습니다.  
  
 **오류 ID:** BC31101  
  
### 이 오류를 해결하려면  
  
-   `Get` 문 또는 `Set` 문에서 액세스 한정자를 제거합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)