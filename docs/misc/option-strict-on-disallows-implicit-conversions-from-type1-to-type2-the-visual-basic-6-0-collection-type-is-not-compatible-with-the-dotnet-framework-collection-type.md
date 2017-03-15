---
title: "Option Strict On에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 암시적으로 변환할 수 없습니다. Visual Basic 6.0의 컬렉션 형식은 .NET Framework의 컬렉션 형식과 호환되지 않습니다. | Microsoft Docs"
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
  - "vbc30753"
  - "bc30753"
helpviewer_keywords: 
  - "BC30753"
ms.assetid: 7e1bb22e-a507-483e-bfd6-f3a43e24a232
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 암시적으로 변환할 수 없습니다. Visual Basic 6.0의 컬렉션 형식은 .NET Framework의 컬렉션 형식과 호환되지 않습니다.
`<type1>`에서는 '`<type2>`'에서 '`Option Strict On`'으로 암시적으로 변환할 수 없습니다. Visual Basic 6.0의 컬렉션 형식은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 컬렉션 형식과 호환되지 않습니다.  
  
 Visual Basic 6.0에서 사용되는 컬렉션 개체는 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]에서 사용되는 컬렉션 개체와 다릅니다.  
  
 **오류 ID:** BC30753  
  
### 이 오류를 해결하려면  
  
-   형식 변환 키워드 중 하나를 사용하여 컬렉션 개체를 명시적으로 변환합니다. 변환에 실패하는 경우 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function) 및 [DirectCast Operator](/dotnet/visual-basic/language-reference/operators/directcast-operator) 키워드가 런타임 예외를 throw합니다. 변환에 실패하는 경우 [TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator) 키워드가 [Nothing](/dotnet/visual-basic/language-reference/nothing)을 반환합니다.  
  
## 참고 항목  
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)   
 [DirectCast Operator](/dotnet/visual-basic/language-reference/operators/directcast-operator)   
 [TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator)   
 [Nothing](/dotnet/visual-basic/language-reference/nothing)   
 [Visual Basic의 NIB 컬렉션](http://msdn.microsoft.com/ko-kr/8b2b7845-2251-4573-8dd3-c9f9c0a66a21)