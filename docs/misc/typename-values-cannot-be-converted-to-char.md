---
title: "&#39;&lt;typename&gt;&#39; 값은 &#39;Char&#39;로 변환 될 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32007"
  - "vbc32007"
helpviewer_keywords: 
  - "BC32007"
ms.assetid: b04212da-57ac-4493-9480-04c12b50f875
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 값은 &#39;Char&#39;로 변환 될 수 없습니다.
'\<typename\>' 값은 Char로 변환 될 수 없습니다. Microsoft.VisualBasic.ChrW를 사용하여 숫자 값을 유니코드 문자로 해석하거나 먼저 숫자 값을 'String'으로 변환하여 숫자를 산출합니다.  
  
 식에서 `String` 또는 `Object` 이외의 데이터 형식을 `Char`로 변환하려고 합니다.  
  
 **오류 ID:** BC32007  
  
### 이 오류를 해결하려면  
  
-   `ChrW` 함수를 사용하여 숫자 값을 유니코드 문자로 변환하거나 먼저 `String`으로 변환한 다음 `Char`로 변환합니다.  
  
## 참고 항목  
 [빌드에 없음: Chr, ChrW 함수](http://msdn.microsoft.com/ko-kr/37f3c707-8a6f-4c51-9b02-9e634c4299ab)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)   
 [Char Data Type](/dotnet/visual-basic/language-reference/data-types/char-data-type)