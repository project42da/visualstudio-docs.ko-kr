---
title: "Math.hypot 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 31488f5a-2230-4114-911e-b6d854c7b0a0
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Math.hypot 함수(JavaScript)
인수 제곱합의 제곱근을 반환합니다.  
  
## 구문  
  
```  
Math.hypot ( value1[, value2[, ...values] );  
```  
  
#### 매개 변수  
 `value1`  
 필수 요소.  첫 번째 숫자입니다.  
  
 `value2`  
 선택적 요소.  두 번째 숫자입니다.  
  
 `values`  
 선택적 요소.  하나 이상의 숫자입니다.  
  
## 설명  
 인수 중 하나가 NaN이면 함수에서 NaN을 반환합니다.  인수가 제공되지 않으면 함수에서 0을 반환합니다.  
  
## 예제  
 다음 예제에서는 `Math.hypot` 함수를 사용하는 예를 보여 줍니다.  
  
```javascript  
Math.hypot(3, 4);  
// Returns 5  
  
Math.hypot(3, "4");  
// Returns 5  
  
Math.hypot(3, "four");  
// Returns NaN   
  
Math.hypot(3, 4, 10);  
// Returns 11.180339887498949  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]