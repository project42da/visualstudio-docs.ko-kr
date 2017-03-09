---
title: "&#39;&lt;typename1&gt;&#39;에서 &#39;&lt;typename2&gt;&#39;로의 암시적 변환입니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42016"
  - "BC42016"
helpviewer_keywords: 
  - "BC42016"
ms.assetid: 7dabaab0-8258-4c17-927f-28e61f50bd3a
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename1&gt;&#39;에서 &#39;&lt;typename2&gt;&#39;로의 암시적 변환입니다.
식 또는 대입문이 한 데이터 형식의 값을 받아서 다른 형식으로 변환합니다. 변환 키워드를 사용하지 않으므로 변환은 *암시적*입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42016  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 변환할 필요가 없도록 동일한 데이터 형식의 값을 사용합니다.  
  
-   변환이 *명시적*이 되도록 `CType` 또는 다른 변환 키워드 중 하나를 사용합니다.  
  
## 참고 항목  
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)   
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)