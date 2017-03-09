---
title: "인수 일치 매개 변수 &#39;&lt;parametername&gt;&#39;이 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 축소됩니다. | Microsoft Docs"
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
  - "vbc30520"
  - "bc30520"
helpviewer_keywords: 
  - "BC30520"
ms.assetid: 652ff70b-156d-4d1c-af19-fa1c53e2d0b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인수 일치 매개 변수 &#39;&lt;parametername&gt;&#39;이 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 축소됩니다.
오버로드된 메서드를 호출했지만 컴파일러에서 축소 변환 없이 호출할 수 있는 메서드를 찾을 수 없습니다. 축소 변환은 가능한 값의 일부를 정확하게 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.  
  
 **오류 ID:** BC30520  
  
### 이 오류를 해결하려면  
  
-   `Option Strict Off`을 지정합니다.  
  
## 참고 항목  
 [Overloaded Properties and Methods](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)