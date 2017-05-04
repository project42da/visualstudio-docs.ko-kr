---
title: "Math.max 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "max"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "max 메서드"
ms.assetid: f3ea1b8a-5fd0-482a-971b-b7f8e2b9b7eb
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# Math.max 함수(JavaScript)
주어진 숫자 식 집합 중 더 큰 값을 반환합니다.  
  
## 구문  
  
```  
Math.max([number1[, number2[... [, numberN]]]])   
```  
  
## 설명  
 선택적인 `number1, number2, ..., numberN` 인수는 실행할 숫자 식입니다.  
  
 인수를 지정하지 않으면 [Number.NEGATIVE\_INFINITY](../../javascript/reference/number-constants-javascript.md)와 같은 값이 반환됩니다.  인수 중 하나가 `NaN`이면 반환 값도 `NaN`입니다.  
  
## 예제  
 다음 코드에서는 두 식 중 더 큰 값을 가져오는 방법을 보여 줍니다.  
  
```javascript  
var x = Math.max(107 - 3,  48 * 90);  
document.write(x);  
  
// Output:  
// 4320  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [Math.min 함수](../../javascript/reference/math-min-function-javascript.md)