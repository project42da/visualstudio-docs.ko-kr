---
title: "&#39;Char&#39; 값을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc32006"
  - "vbc32006"
helpviewer_keywords: 
  - "BC32006"
ms.assetid: c033f65e-a315-47fc-be2e-ed371847a221
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Char&#39; 값을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다.
'Char' 값을 '\<typename\>'으로 변환할 수 없습니다. Microsoft.VisualBasic.AscW를 사용하여 문자를 유니코드 값으로 해석하거나 Microsoft.VisualBasic.Val을 사용하여 문자를 숫자로 해석하세요.  
  
 식에서 `Char` 값을 `String` 또는 `Object` 이외의 데이터 형식으로 변환하려고 합니다.  
  
 **오류 ID:** BC32006  
  
### 이 오류를 해결하려면  
  
-   `AscW` 함수를 사용하여 `Char` 값을 유니코드 문자 코드로 해석하거나 `Val` 함수를 사용하여 숫자로 해석합니다.  
  
## 참고 항목  
 [빌드에 없음: Asc, AscW 함수](http://msdn.microsoft.com/ko-kr/6814bfec-12ba-41fb-b10e-bec99750d5e1)   
 [빌드에 없음: Val 함수](http://msdn.microsoft.com/ko-kr/81650f77-9242-4ec1-8e04-e93b5daa451d)   
 [Char Data Type](/dotnet/visual-basic/language-reference/data-types/char-data-type)