---
title: "Option Strict On에서는 런타임에 바인딩을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30574"
  - "vbc30574"
helpviewer_keywords: 
  - "BC30574"
ms.assetid: 9da4b826-2e12-4a5d-9e17-762b0b68fc9b
caps.latest.revision: 11
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 런타임에 바인딩을 사용할 수 없습니다.
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 모든 데이터 형식을 다른 데이터 형식으로 암시적으로 변환할 수 있습니다. 그러나 한 데이터 형식의 값을 정밀도나 용량이 더 적은 데이터 형식으로 변환할 경우 데이터가 손실될 수 있습니다.`Option Strict On`을 사용하면 이러한 유형의 변환을 방지할 수 있도록 컴파일 시간 알림이 제공됩니다. 런타임에 바인딩과 함께 `Option Strict On`을 사용할 수 없습니다.  
  
 다음 코드 예제에서는 런타임에 바인딩을 사용하며 `Option Strict`가 `On`으로 설정된 경우 이 오류가 발생합니다.  
  
 [!CODE [VbVbalrOptionStrictError#1](VbVbalrOptionStrictError#1)]  
  
 **오류 ID:** BC30574  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 명시적 형식을 사용하도록 개체 선언을 수정합니다.  
  
     [!CODE [VbVbalrOptionStrictError#2](VbVbalrOptionStrictError#2)]  
  
 또는  
  
-   다음 예제와 같이 명시적 형식을 사용하도록 런타임에 바인딩 식을 수정합니다.  
  
     [!CODE [VbVbalrOptionStrictError#3](VbVbalrOptionStrictError#3)]  
  
 또는  
  
-   다음 예제와 같이 컴파일러가 특정 형식을 유추할 수 있도록 합니다.  
  
     [!CODE [VbVbalrOptionStrictError#4](VbVbalrOptionStrictError#4)]  
  
 또는  
  
-   뒤에 있는 `On` 단어를 제거하거나 명시적으로 `Off`를 지정하여 `Option Strict`를 끕니다.  
  
## 참고 항목  
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)