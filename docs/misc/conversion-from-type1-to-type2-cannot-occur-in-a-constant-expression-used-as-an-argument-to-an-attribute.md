---
title: "특성에 대한 인수로 사용된 상수 식에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc30934"
  - "vbc30934"
helpviewer_keywords: 
  - "BC30934"
ms.assetid: 120e05f9-1d0e-4800-b05c-a8373e286b9b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성에 대한 인수로 사용된 상수 식에서는 &#39;&lt;type1&gt;&#39;에서 &#39;&lt;type2&gt;&#39;로 변환할 수 없습니다.
특성 인수에 사용되는 식이 해당 특성 매개 변수의 데이터 형식과 다른 데이터 형식으로 계산되며, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 특성 인수에 대한 필수 형식 변환을 허용하지 않습니다.  
  
 특성은 해당 특성이 적용되는 요소에 대한 메타데이터를 제공하며, 컴파일러가 컴파일 시간에 모든 메타데이터를 생성할 수 있어야 합니다. 이러한 이유로 모든 특성은 컴파일 시간에 상수인 값을 사용해야 하므로 모든 특성 인수가 컴파일 시간 상수 값으로 계산되어야 합니다.  
  
 특정 형식 변환은 컴파일 시간에 상수인 값을 생성할 수 없습니다. 예를 들어 `String`을 `Double` 또는 `Date`로 변환할지 여부는 런타임의 로캘 설정에 따라 달라집니다. 파생 형식 배열을 `Object` 배열로 변환 등의 기타 변환에서는 컴파일러가 특성 인수에서 허용할 수 없도록 하는 다양한 문제가 발생합니다.  
  
 **오류 ID:** BC30934  
  
### 이 오류를 해결하려면  
  
-   특성에 정의된 대로 해당 매개 변수와 동일한 데이터 형식으로 계산되는 식을 사용합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Const Statement](/dotnet/visual-basic/language-reference/statements/const-statement)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)