---
title: "속성 접근자는 &#39;Default&#39; 속성에서 &#39;&lt;accessmodifier&gt;&#39;가 선언될 수 없습니다. | Microsoft Docs"
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
  - "bc31107"
  - "vbc31107"
helpviewer_keywords: 
  - "BC31107"
ms.assetid: 25657b33-df85-4535-8043-69795c987175
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 속성 접근자는 &#39;Default&#39; 속성에서 &#39;&lt;accessmodifier&gt;&#39;가 선언될 수 없습니다.
기본 속성의 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 또는 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)은 `Private` 키워드를 포함합니다.  
  
 기본 속성은 `Private`이 될 수 없으며 해당 개별 속성 프로시저\(`Get` 또는 `Set`\)도 될 수 없습니다.  
  
 **오류 ID:** BC31107  
  
### 이 오류를 해결하려면  
  
-   `Get` 또는 `Set` 문에서 `Private` 키워드를 제거하거나 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)에서 `Default`을 제거합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)   
 [How to: Declare and Call a Default Property in Visual Basic](../Topic/How%20to:%20Declare%20and%20Call%20a%20Default%20Property%20in%20Visual%20Basic.md)