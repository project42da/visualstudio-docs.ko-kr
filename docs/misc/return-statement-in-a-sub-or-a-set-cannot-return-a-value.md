---
title: "Sub 또는 Set의 &#39;Return&#39; 문은 값을 반환할 수 없습니다. | Microsoft Docs"
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
  - "bc30647"
  - "vbc30647"
helpviewer_keywords: 
  - "BC30647"
ms.assetid: d4c05c28-d650-4f49-976e-650d84802036
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub 또는 Set의 &#39;Return&#39; 문은 값을 반환할 수 없습니다.
`Sub` 프로시저 및 속성 `Set` 프로시저는 값을 반환할 수 없습니다.  
  
 **오류 ID:** BC30647  
  
### 이 오류를 해결하려면  
  
-   현재 프로시저가 속성의 일부인 경우 현재 프로시저를 함수 또는 `Get` 속성 프로시저로 변경합니다.  
  
-   `ByRef` 키워드를 사용하여 참조에 의해 전달된 매개 변수 값을 수정하면 `Sub` 프로시저에서 효과적으로 값을 반환할 수 있습니다.  
  
## 참고 항목  
 [Return Statement](/dotnet/visual-basic/language-reference/statements/return-statement)   
 [Sub Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/sub-procedures)   
 [Function 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/function-procedures)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)