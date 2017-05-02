---
title: "Number 상수(JavaScript) | Microsoft Docs"
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
  - "상수[JavaScript], 숫자"
  - "MAX_VALUE 상수[JavaScript]"
  - "MIN_VALUE 상수[JavaScript]"
  - "NaN 상수[JavaScript]"
  - "NEGATIVE_INFINITY 상수[JavaScript]"
  - "number 상수[JavaScript]"
  - "Number.MAX_VALUE 상수[JavaScript]"
  - "Number.MIN_VALUE 상수[JavaScript]"
  - "Number.NaN 상수[JavaScript]"
  - "Number.NEGATIVE_INFINITY 상수[JavaScript]"
  - "Number.POSITIVE_INFINITY 상수[JavaScript]"
  - "POSITIVE_INFINITY 상수[JavaScript]"
ms.assetid: e0701b41-99ae-4916-9ec0-f79bb15386fb
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# Number 상수(JavaScript)
다음 숫자 상수는 `Number` 개체의 속성입니다.  
  
## Number 개체 상수  
 이런 상수에 액세스하기 위해 `Number` 개체를 만들 필요는 없습니다.  
  
|상수|반환된 값|  
|--------|-----------|  
|`Number.EPSILON`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 작은 수입니다.  약 2.2204460492503130808472633361816E\-16과 같습니다.|  
|`Number.MAX_SAFE_INTEGER`|JavaScript로 안전하게 나타낼 수 있는 가장 큰 수입니다.  9007199254740991과 같습니다.|  
|`Number.MAX_VALUE`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 수입니다.  약 1.79E\+308과 같습니다.|  
|`Number.MIN_SAFE_INTEGER`|JavaScript로 안전하게 나타낼 수 있는 가장 작은 수입니다.  −9007199254740991과 같습니다.|  
|`Number.MIN_VALUE`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 0에 가장 가까운 수입니다.  약 5.00E\-324와 같습니다.|  
|`Number.NaN`|숫자가 아닌 값입니다.<br /><br /> 같음 비교에서, `NaN`은 그 자신을 포함하여 어떤 값과 같지 않습니다.  값이 `NaN`과 동일한지 테스트하기 위해 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)를 사용하세요.|  
|`Number.NEGATIVE_INFINITY`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 음수보다 작은 값입니다.<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 `NEGATIVE_INFINITY` 값을 `-infinity`로 표시합니다.|  
|`Number.POSITIVE_INFINITY`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 수보다 큰 값입니다.<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 `POSITIVE_INFINITY` 값을 `infinity`로 표시합니다.|  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 `Number.EPSILON`, `Number.MAX_SAFE_INTEGER` 및 `Number.MIN_SAFE_INTEGER`의 경우:  
  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)  
  
## 참고 항목  
 [Math 상수](../../javascript/reference/math-constants-javascript.md)   
 [JavaScript 상수](../../javascript/reference/javascript-constants.md)   
 [Infinity 상수](../../javascript/reference/infinity-constant-javascript.md)   
 [NaN 상수](../../javascript/reference/nan-constant-javascript.md)   
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)