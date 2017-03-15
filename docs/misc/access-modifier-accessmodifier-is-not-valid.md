---
title: "액세스 한정자 &#39;&lt;accessmodifier&gt;&#39;가 올바르지 않습니다. | Microsoft Docs"
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
  - "bc31100"
  - "vbc31100"
helpviewer_keywords: 
  - "BC31100"
ms.assetid: 1cd71acc-0b54-4f64-8d61-75b272d293cb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 액세스 한정자 &#39;&lt;accessmodifier&gt;&#39;가 올바르지 않습니다.
[Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 또는 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)에서 포함하는 속성에 대해 지정한 수준보다 덜 제한적인 액세스 수준을 지정합니다.  
  
 언제든지 속성에 대한 액세스 수준을 지정할 수 있습니다. 또한 속성의 액세스 수준보다 더 제한적인 경우 해당 속성 프로시저\(`Get` 또는 `Set`\) 중 최대 하나에 대해 다른 액세스 수준을 지정할 수 있습니다. 예를 들어 속성이 `Friend`인 경우 속성 프로시저에 대해 `Public`이 아닌 `Private`을 지정할 수 있습니다. 두 속성 프로시저 모두에 대해 액세스 수준을 지정할 수는 없습니다.  
  
 **오류 ID:** BC31100  
  
### 이 오류를 해결하려면  
  
-   속성 프로시저에 대한 액세스 수준을 속성보다 더 제한적으로 지정하거나 액세스 한정자를 완전히 제거합니다.  
  
-   [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)에서 낮은 액세스 제한 수준을 선언하고 속성 프로시저 중 하나에서 높은 액세스 제한 수준을 선언합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)