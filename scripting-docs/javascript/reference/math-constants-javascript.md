---
title: "Math 상수(JavaScript) | Microsoft Docs"
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
helpviewer_keywords: 
  - "LN2 상수[JavaScript]"
  - "E 상수[JavaScript]"
  - "LOG10E 상수[JavaScript]"
  - "SQRT1_2 상수[JavaScript]"
  - "LOG2E 상수[JavaScript]"
  - "Math.SQRT2 상수[JavaScript]"
  - "PI 상수[JavaScript]"
  - "Math.LOG2E 상수[JavaScript]"
  - "상수[JavaScript], math"
  - "Math.E 상수[JavaScript]"
  - "로그 상수[JavaScript]"
  - "Math.LOG10E 상수[JavaScript]"
  - "Math.SQRT1_2 상수[JavaScript]"
  - "SQRT2 상수[JavaScript]"
  - "제곱근 상수[JavaScript]"
  - "Math.PI 상수[JavaScript]"
  - "math 상수[JavaScript]"
  - "LN10 상수[JavaScript]"
  - "Math.LN2 상수[JavaScript]"
  - "Math.LN10 상수[JavaScript]"
ms.assetid: 8a674046-cb99-4103-92be-83697fba6344
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Math 상수(JavaScript)
수학 상수는 `Math` 개체의 속성인 상수 값을 반환합니다.  
  
## Math 개체 상수  
 다음 표에서는 [Math 개체](../../javascript/reference/math-object-javascript.md)의 속성인 상수 값을 보여 줍니다.  
  
|상수|설명|근사값|  
|--------|--------|---------|  
|`Math.E`|수학 상수 e입니다.  자연 로그의 밑인 Euler의 상수입니다.|2.718|  
|`Math.LN2`|2의 자연 로그입니다.|0.693|  
|`Math.LN10`|10의 자연 로그입니다.|2.302|  
|`Math.LOG2E`|밑이 2인 e의 로그입니다.|1.443|  
|`Math.LOG10E`|밑이 10인 e의 로그입니다.|0.434|  
|`Math.PI`|Pi.  원주율입니다.|3.14159|  
|`Math.SQRT1_2`|0.5의 제곱근 값 또는 1을 2의 제곱근으로 나눈 값입니다.|0.707|  
|`Math.SQRT2`|2의 제곱근입니다.|1.414|  
  
## 예제  
 다음 예제에서는 `Math.PI` 상수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var radius = 3;  
var area = Math.PI * radius * radius;  
document.write(area);  
  
// Output: 28.274333882308138  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## 참고 항목  
 [Number 상수](../../javascript/reference/number-constants-javascript.md)   
 [JavaScript 상수](../../javascript/reference/javascript-constants.md)