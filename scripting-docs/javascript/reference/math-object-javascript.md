---
title: "Math 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Math object
ms.assetid: 607b94cb-921c-43cd-b514-fdbc13aeced6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f16fe4edf6a2a49db15d74abc8ebe6e53f955710
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="math-object-javascript"></a>Math 개체(JavaScript)
기본적인 수학 기능과 상수를 제공하는 내장 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Math.[{property | method}]  
```  
  
## <a name="parameters"></a>매개 변수  
 *속성*  
 필수 요소. 속성 중 하나의 이름을 **수학**합니다. 이름입니다.  
  
 *메서드*  
 필수 요소. 메서드 중 하나의 이름을 **수학**합니다. 이름입니다.  
  
## <a name="remarks"></a>설명  
 **수학** 를 사용 하 여 개체를 만들 수는 **새** 연산자를 이렇게 하려고 하면 오류가 발생 합니다. 엔진이 로드될 때 스크립팅 엔진에서 이 개체를 만듭니다. 이 개체의 모든 메서드와 속성은 스크립트에 항상 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 `Math` 개체는 [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]에서 도입되었습니다.  
  
<a name="js56jsobjmathprop"></a>   
## <a name="constants"></a>상수  
 다음 표에서는 `Math` 개체의 상수를 보여줍니다.  
  
|상수|설명|  
|--------------|-----------------|  
|[Math.E 상수](../../javascript/reference/math-constants-javascript.md)|산술 상수 e입니다. 자연 로그의 밑인 오일러의 수입니다.|  
|[Math.LN2 상수](../../javascript/reference/math-constants-javascript.md)|자연 로그 2입니다.|  
|[Math.LN10 상수](../../javascript/reference/math-constants-javascript.md)|자연 로그 10입니다.|  
|[Math.LOG2E 상수](../../javascript/reference/math-constants-javascript.md)|base-2 로그 e입니다.|  
|[Math.LOG10E 상수](../../javascript/reference/math-constants-javascript.md)|base-10 로그 e입니다.|  
|[Math.PI 상수](../../javascript/reference/math-constants-javascript.md)|Pi. 지름의 비인 Pi(파이)입니다.|  
|[Math.SQRT1_2 상수](../../javascript/reference/math-constants-javascript.md)|1을 2의 제곱근으로 나눈 값에 해당하는 0.5의 제곱근입니다.|  
|[Math.SQRT2 상수](../../javascript/reference/math-constants-javascript.md)|2의 제곱근입니다.|  
  
<a name="js56jsobjmathmeth"></a>   
## <a name="functions"></a>함수  
 다음 표에서는 `Math` 개체의 함수를 보여줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[Math.abs 함수](../../javascript/reference/math-abs-function-javascript.md)|숫자의 절대값을 반환합니다.|  
|[Math.acos 함수](../../javascript/reference/math-acos-function-javascript.md)|숫자의 아크코사인을 반환합니다.|  
|[Math.acosh 함수](../../javascript/reference/math-acosh-function-javascript.md)|숫자의 쌍곡 아크코사인(또는 쌍곡선 역코사인)을 반환합니다.|  
|[Math.asin 함수](../../javascript/reference/math-asin-function-javascript.md)|숫자의 아크사인을 반환합니다.|  
|[Math.asinh 함수](../../javascript/reference/math-asinh-function-javascript.md)|숫자의 역쌍곡 사인을 반환합니다.|  
|[Math.atan 함수](../../javascript/reference/math-atan-function-javascript.md)|숫자의 아크탄젠트를 반환합니다.|  
|[Math.atan2 함수](../../javascript/reference/math-atan2-function-javascript.md)|X 축에서 입력한 y 및 x 좌표로 표시되는 점까지의 각도를 라디안으로 반환합니다.|  
|[Math.atanh 함수](../../javascript/reference/math-atanh-function-javascript.md)|숫자의 역쌍곡 탄젠트를 반환합니다.|  
|[Math.ceil 함수](../../javascript/reference/math-ceil-function-javascript.md)|입력한 숫자 식 이상의 최소 정수를 반환합니다.|  
|[Math.cos 함수](../../javascript/reference/math-cos-function-javascript.md)|숫자의 코사인을 반환합니다.|  
|[Math.cosh 함수](../../javascript/reference/math-cosh-function-javascript.md)|숫자의 쌍곡 코사인을 반환합니다.|  
|[Math.exp 함수](../../javascript/reference/math-exp-function-javascript.md)|반환 *e* (자연 로그의 밑) 거듭제곱 합니다.|  
|[Math.expm1 함수](../../javascript/reference/math-expm1-function-javascript.md)|e(자연 로그의 밑) 거듭제곱에서 1을 뺀 결과를 반환합니다.)|  
|[Math.floor 함수](../../javascript/reference/math-floor-function-javascript.md)|입력한 숫자 식 이하의 최대 정수를 반환합니다.|  
|[Math.hypot 함수](../../javascript/reference/math-hypot-function-javascript.md)|인수 제곱합의 제곱근을 반환합니다.|  
|[Math.imul 함수](../../javascript/reference/math-imul-function-javascript.md)|32비트 부호 있는 정수로 처리되는 두 숫자의 곱을 반환합니다.|  
|[Math.log 함수](../../javascript/reference/math-log-function-javascript.md)|숫자의 자연 로그를 반환합니다.|  
|[Math.log1p 함수](../../javascript/reference/math-log1p-function-javascript.md)|1 + 숫자의 자연 로그를 반환합니다.|  
|[Math.log10 함수](../../javascript/reference/math-log10-function-javascript.md)|숫자의 밑이 10인 로그 값을 반환합니다.|  
|[Math.log2 함수](../../javascript/reference/math-log2-function-javascript.md)|숫자의 밑이 2인 로그 값을 반환합니다.|  
|[Math.max 함수](../../javascript/reference/math-max-function-javascript.md)|입력한 두 숫자 식 중 더 큰 항목을 반환합니다.|  
|[Math.min 함수](../../javascript/reference/math-min-function-javascript.md)|입력한 두 숫자 중 더 작은 항목을 반환합니다.|  
|[Math.pow 함수](../../javascript/reference/math-pow-function-javascript.md)|지정한 거듭제곱으로 반올림된 기본 식의 값을 반환합니다.|  
|[Math.random 함수](../../javascript/reference/math-random-function-javascript.md)|0에서 1 사이의 의사 난수를 반환합니다.|  
|[Math.round 함수](../../javascript/reference/math-round-function-javascript.md)|가장 가까운 정수로 반올림된 지정한 숫자 식을 반환합니다.|  
|[Math.sign 함수](../../javascript/reference/math-sign-function-javascript.md)|숫자가 양수, 음수 또는 0인지를 나타내는 숫자의 부호를 반환합니다.|  
|[Math.sin 함수](../../javascript/reference/math-sin-function-javascript.md)|숫자의 사인을 반환합니다.|  
|[Math.sinh 함수](../../javascript/reference/math-sinh-function-javascript.md)|숫자의 역쌍곡 사인을 반환합니다.|  
|[Math.sqrt 함수](../../javascript/reference/math-sqrt-function-javascript.md)|숫자의 제곱근을 반환합니다.|  
|[Math.tan 함수](../../javascript/reference/math-tan-function-javascript.md)|숫자의 탄젠트를 반환합니다.|  
|[Math.tanh 함수](../../javascript/reference/math-tanh-function-javascript.md)|숫자의 쌍곡 탄젠트를 반환합니다.|  
|[Math.trunc 함수](../../javascript/reference/math-trunc-function-javascript.md)|소수 자릿수를 제거하고 숫자의 정수 부분을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 개체](../../javascript/reference/javascript-objects.md)   
 [Number 개체](../../javascript/reference/number-object-javascript.md)