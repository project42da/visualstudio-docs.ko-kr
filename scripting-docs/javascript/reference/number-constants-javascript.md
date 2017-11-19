---
title: "숫자 상수 (JavaScript) | Microsoft Docs"
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
- POSITIVE_INFINITY constant [JavaScript]
- MAX_VALUE constant [JavaScript]
- MIN_VALUE constant [JavaScript]
- number constants [JavaScript]
- Number.NEGATIVE_INFINITY constant [JavaScript]
- Number.POSITIVE_INFINITY constant [JavaScript]
- NEGATIVE_INFINITY constant [JavaScript]
- NaN constant [JavaScript]
- Number.MIN_VALUE constant [JavaScript]
- constants [JavaScript], number
- Number.NaN constant [JavaScript]
- Number.MAX_VALUE constant [JavaScript]
ms.assetid: e0701b41-99ae-4916-9ec0-f79bb15386fb
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f846ef7cbd9609f7913d6305e48cb4942476ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="number-constants-javascript"></a>Number 상수(JavaScript)
다음 숫자 상수는 `Number` 개체의 속성입니다.  
  
## <a name="number-object-constants"></a>Number 개체 상수  
 이런 상수에 액세스하기 위해 `Number` 개체를 만들 필요는 없습니다.  
  
|상수|반환된 값|  
|--------------|--------------------|  
|`Number.EPSILON`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 작은 수입니다. 약 2.2204460492503130808472633361816E-16과 같습니다.|  
|`Number.MAX_SAFE_INTEGER`|JavaScript로 안전하게 나타낼 수 있는 가장 큰 수입니다. 9007199254740991과 같습니다.|  
|`Number.MAX_VALUE`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 수입니다. 약 1.79E+308과 같습니다.|  
|`Number.MIN_SAFE_INTEGER`|JavaScript로 안전하게 나타낼 수 있는 가장 작은 수입니다. -9007199254740991과 같습니다.|  
|`Number.MIN_VALUE`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 0에 가장 가까운 수입니다. 약 5.00E-324와 같습니다.|  
|`Number.NaN`|숫자가 아닌 값입니다.<br /><br /> 같음 비교에서, `NaN`은 그 자신을 포함하여 어떤 값과 같지 않습니다. 에 해당 하는 값이 있는지 여부를 테스트 `NaN`를 사용 하 여는 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)합니다.|  
|`Number.NEGATIVE_INFINITY`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 음수보다 작은 값입니다.<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 `NEGATIVE_INFINITY` 값을 `-infinity`로 표시합니다.|  
|`Number.POSITIVE_INFINITY`|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]로 나타낼 수 있는 가장 큰 수보다 큰 값입니다.<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 `POSITIVE_INFINITY` 값을 `infinity`로 표시합니다.|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 `Number.EPSILON`, `Number.MAX_SAFE_INTEGER` 및 `Number.MIN_SAFE_INTEGER`의 경우:  
  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Math 상수](../../javascript/reference/math-constants-javascript.md)   
 [JavaScript 상수](../../javascript/reference/javascript-constants.md)   
 [Infinity 상수](../../javascript/reference/infinity-constant-javascript.md)   
 [NaN 상수](../../javascript/reference/nan-constant-javascript.md)   
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)