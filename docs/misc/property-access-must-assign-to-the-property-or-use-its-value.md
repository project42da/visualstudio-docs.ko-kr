---
title: "속성 액세스를 속성에 할당하거나 속성 액세스에서 속성 값을 사용해야 합니다. | Microsoft Docs"
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
  - "bc30545"
  - "vbc30545"
helpviewer_keywords: 
  - "BC30545"
ms.assetid: df271c05-1e7a-44e8-bf53-79f06ef916ab
caps.latest.revision: 11
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 속성 액세스를 속성에 할당하거나 속성 액세스에서 속성 값을 사용해야 합니다.
속성에 할당하거나 해당 값을 사용하지 않고 속성에 액세스하려고 했습니다. 다음 코드는 예제를 제공합니다.  
  
 [!CODE [VbVbalrErrorSamples#1](VbVbalrErrorSamples#1)]  
  
 **오류 ID:** BC30545  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 속성에 값을 할당합니다.  
  
     [!CODE [VbVbalrErrorSamples#3](VbVbalrErrorSamples#3)]  
  
     또는  
  
-   다음 예제와 같이 속성의 값을 사용합니다.  
  
     [!CODE [VbVbalrErrorSamples#2](VbVbalrErrorSamples#2)]  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [Assignment Operators](/dotnet/visual-basic/language-reference/operators/assignment-operators)