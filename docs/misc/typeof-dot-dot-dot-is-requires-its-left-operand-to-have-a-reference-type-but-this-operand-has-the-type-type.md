---
title: "&#39;TypeOf ... Is&#39;의 왼쪽 피연산자는 참조 형식이어야 하는데 이 피연산자의 형식은 &#39;&lt;type&gt;&#39;입니다. | Microsoft Docs"
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
  - "bc30021"
  - "vbc30021"
helpviewer_keywords: 
  - "BC30021"
ms.assetid: a6e76fc8-9c7f-4e55-8b68-e6e7b03a6737
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;TypeOf ... Is&#39;의 왼쪽 피연산자는 참조 형식이어야 하는데 이 피연산자의 형식은 &#39;&lt;type&gt;&#39;입니다.
`TypeOf...Is` 식은 개체 변수의 런타임 형식 호환성을 검사합니다. 이 호환성은 값 형식에 대해 정의되지 않았습니다.  
  
 **오류 ID:** BC30021  
  
### 이 오류를 해결하려면  
  
-   `Option Strict`가 `Off`인 경우 `TypeName` 또는 `VarType` 함수를 사용하여 변수의 데이터 형식 정보를 가져옵니다.  
  
-   `Option Strict`가 `On`인 경우 변수 선언을 통해 변수의 데이터 형식이 결정됩니다.  
  
## 참고 항목  
 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)   
 [빌드에 없음: TypeName 함수\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/6197bc6c-e8a6-4711-883c-0c95e94e272c)   
 [빌드에 없음: VarType 함수\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/e820b6fc-faa6-4de4-836a-0466032dc190)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)