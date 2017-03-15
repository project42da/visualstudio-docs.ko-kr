---
title: "&#39;&lt;typename&gt;&#39; 형식은 &#39;For&#39; 문에서 사용하는 &#39;&lt;operator&gt;&#39; 연산자를 정의해야 합니다. | Microsoft Docs"
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
  - "vbc33038"
  - "BC33038"
helpviewer_keywords: 
  - "BC33038"
ms.assetid: b1c9d87f-80f9-4c8c-8908-f8400b9fe4c5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 &#39;For&#39; 문에서 사용하는 &#39;&lt;operator&gt;&#39; 연산자를 정의해야 합니다.
`For` 루프에서 필요한 연산자를 지원하지 않는 유형의 카운터 변수를 지정합니다.  
  
 `For` 루프의 카운터 변수는 다음 연산자를 모두 지원하는 데이터 형식일 수 있습니다.  
  
-   크거나 같음\(`>=`\)  
  
-   작거나 같음\(`<=`\)  
  
-   더하기\(`+`\)  
  
-   빼기\(`-`\)  
  
 카운터 변수에 숫자 데이터 형식을 사용하면 위의 연산자가 모두 지원됩니다. 사용자 정의 클래스 또는 구조체를 사용하면 해당 클래스나 구조체에 위의 연산자를 모두 정의해야 합니다.  
  
 또한 `For` 문에서 `start`, `end` 및 `step` 식의 데이터 형식이 카운터 변수의 데이터 형식으로 확장되어야 합니다. 카운터 변수가 사용자 정의 클래스나 구조체이고 `start`, `end` 또는 `step` 식이 다른 형식일 경우 `CType` 변환 연산자를 정의하여 필요한 변환을 수행해야 합니다.  
  
 **오류 ID:** BC33038  
  
### 이 오류를 해결하려면  
  
1.  카운터 변수 데이터 형식의 철자가 올바른지 확인합니다.  
  
2.  카운터 변수에 사용자 정의 클래스 또는 구조체를 사용할 경우 해당 클래스나 구조체에 필요한 모든 연산자를 정의합니다.  
  
3.  `start`, `end` 및 `step` 식의 데이터 형식에 따라 하나 이상의 `CType` 변환 연산자를 정의하여 카운터 변수 데이터 형식으로 변환해야 합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)