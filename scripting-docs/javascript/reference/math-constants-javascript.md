---
title: "Math 상수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- LN2 constant [JavaScript]
- E constant [JavaScript]
- LOG10E constant [JavaScript]
- SQRT1_2 constant [JavaScript]
- LOG2E constant [JavaScript]
- Math.SQRT2 constant [JavaScript]
- PI constant [JavaScript]
- Math.LOG2E constant [JavaScript]
- constants [JavaScript], math
- Math.E constant [JavaScript]
- logarithm consants [JavaScript]
- Math.LOG10E constant [JavaScript]
- Math.SQRT1_2 constant [JavaScript]
- SQRT2 constant [JavaScript]
- square root constants [JavaScript]
- Math.PI constant [JavaScript]
- math constants [JavaScript]
- LN10 constant [JavaScript]
- Math.LN2 constant [JavaScript]
- Math.LN10 constant [JavaScript]
ms.assetid: 8a674046-cb99-4103-92be-83697fba6344
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9942abb69af416cd4cd7f092dc9f1478e0bc3a69
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="math-constants-javascript"></a>Math 상수(JavaScript)
속성인 상수 값을 반환 하는 수학 상수는 `Math` 개체입니다.  
  
## <a name="math-object-constants"></a>Math 개체 상수  
 다음 표에서 상수 값의 속성을 나열는 [Math 개체](../../javascript/reference/math-object-javascript.md)합니다.  
  
|상수|설명|대략적인 값|  
|--------------|-----------------|-----------------------|  
|`Math.E`|산술 상수 e입니다. 자연 로그의 밑인 오일러의 수입니다.|2.718|  
|`Math.LN2`|자연 로그 2입니다.|0.693|  
|`Math.LN10`|자연 로그 10입니다.|2.302|  
|`Math.LOG2E`|base-2 로그 e입니다.|1.443|  
|`Math.LOG10E`|base-10 로그 e입니다.|0.434|  
|`Math.PI`|Pi. 지름의 비인 Pi(파이)입니다.|3.14159|  
|`Math.SQRT1_2`|1을 2의 제곱근으로 나눈 값에 해당하는 0.5의 제곱근입니다.|0.707|  
|`Math.SQRT2`|2의 제곱근입니다.|1.414|  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `Math.PI` 상수입니다.  
  
```JavaScript  
var radius = 3;  
var area = Math.PI * radius * radius;  
document.write(area);  
  
// Output: 28.274333882308138  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Number 상수](../../javascript/reference/number-constants-javascript.md)   
 [JavaScript 상수](../../javascript/reference/javascript-constants.md)