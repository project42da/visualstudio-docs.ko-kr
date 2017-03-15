---
title: "&#39;&lt;typename&gt;&#39; 형식의 식은 &#39;Object&#39; 또는 &#39;ValueType&#39;으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc31394"
  - "vbc31394"
helpviewer_keywords: 
  - "BC31394"
ms.assetid: e6f76257-65bb-4954-99f9-90f282648354
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식의 식은 &#39;Object&#39; 또는 &#39;ValueType&#39;으로 변환할 수 없습니다.
식이 CLR\(공용 언어 런타임\)에서 boxing될 수 없는 형식으로 계산합니다.  
  
 *Boxing*은 형식을 경우에 따라 `Object` 또는 <xref:System.ValueType>으로 변환하는 데 필요한 처리를 참조합니다. 공용 언어 런타임에서 특정 형식\(예: <xref:System.ArgIterator> 및 <xref:System.TypedReference>\)을 boxing할 수 없습니다.  
  
 이 식을 포함하는 문에서 `CType` 또는 `CObj`를 사용하지 않은 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 이 오류를 발생시키는 암시적인 변환을 시도했습니다.  
  
 **오류 ID:** BC31394  
  
### 이 오류를 해결하려면  
  
1.  제시된 형식으로 계산되는 식을 찾습니다.  
  
2.  제시된 형식을 boxing하려는 문의 일부를 찾습니다.  
  
3.  Boxing 변환을 방지하려면 문을 다시 작성합니다.  
  
## 참고 항목  
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)