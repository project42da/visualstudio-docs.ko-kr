---
title: "Math.min 함수(JavaScript) | Microsoft Docs"
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
  - "min"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "min 메서드"
ms.assetid: a1d7dd85-27ef-45cd-aa2a-f8e80f0b2898
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# Math.min 함수(JavaScript)
숫자 식 집합 중 작은 식을 반환합니다.  
  
## 구문  
  
```  
Math.min([number1[, number2[... [,numberN]]]])  
```  
  
## 설명  
 선택적인 `number1, number2, ..., numberN` 인수는 실행할 숫자 식입니다.  
  
 인수가 지정되지 않으면 [Number.POSITIVE\_INFINITY](../../javascript/reference/number-constants-javascript.md)와 같은 값을 반환합니다.  인수 중 하나가 `NaN`이면 반환 값도 `NaN`입니다.  
  
## 예제  
 다음 코드에서는 두 식 중 작은 식을 가져오는 방법을 보여 줍니다.  
  
```javascript  
var x = Math.min(107 - 3, 48 * 90);  
document.write(x);  
  
// Output:  
// 104  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [Math.max 함수](../../javascript/reference/math-max-function-javascript.md)