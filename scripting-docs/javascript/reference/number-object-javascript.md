---
title: "Number 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Number_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Number object
ms.assetid: 76e87c37-cf6c-46cc-bafa-04be1fe3d78d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cbe58fdc9673a8fffe35b8b15d7edbf86ffa655
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="number-object-javascript"></a>Number 개체(JavaScript)
임의 종류의 숫자를 나타내는 개체입니다. 모든 JavaScript 숫자는 64비트 부동 소수점 숫자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
numObj = new Number(value)  
```  
  
## <a name="parameters"></a>매개 변수  
 `numObj`  
 필수 요소. `Number` 개체가 할당되는 변수 이름입니다.  
  
 `value`  
 필수 요소. 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 변수가 숫자 값(예: `var num = 255.336;`)으로 설정된 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]서 `Number` 개체를 만듭니다. `Number` 개체를 명시적으로 만들 필요는 거의 없습니다.  
  
 `Number` 개체에는 `Object`에서 상속된 속성 및 메서드뿐 아니라 고유한 속성 및 메서드가 있습니다. 숫자를 추가하거나 문자열에 연결하는 경우와 같은 특정 상황에서 및 `toString` 메서드를 통해 숫자가 문자열로 변환됩니다. 자세한 내용은 참조 [더하기 연산자 (+)](../../javascript/reference/addition-operator-decrement-javascript.md)합니다.  
  
 JavaScript에는 여러 숫자 상수가 있습니다. 전체 목록을 보려면를 참조 하십시오. [숫자 상수는](../../javascript/reference/number-constants-javascript.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Number` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[constructor 속성](../../javascript/reference/constructor-property-object-javascript.md)|개체를 만드는 함수를 지정합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-object-javascript.md)|개체 클래스의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="functions"></a>함수  
 다음 표에서의 함수는 `Number` 개체입니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[Number.isFinite 함수](../../javascript/reference/number-isfinite-function-number-javascript.md)|값이 유한한지 여부를 나타내는 부울 값을 반환합니다.|  
|[Number.isInteger 함수](../../javascript/reference/number-isinteger-function-number-javascript.md)|값이 정수인지 여부를 나타내는 부울 값을 반환합니다.|  
|[Number.isNaN 함수](../../javascript/reference/number-isnan-function-number-javascript.md)|값이 예약된 값 `NaN`(숫자 아님)인지 여부를 나타내는 부울 값을 반환합니다.|  
|[Number.isSafeInteger](../../javascript/reference/number-issafeinteger-number-javascript.md)|값이 JavaScript에서 안전하게 표현될 수 있는지를 나타내는 부울 값을 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드가 나열 된 `Number` 개체입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 계층 구조에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지 여부 및 열거 가능한지 여부를 나타내는 부울 값을 반환합니다.|  
|[toExponential 메서드](../../javascript/reference/toexponential-method-number-javascript.md)|지수 표기법으로 표현된 숫자를 포함하는 문자열을 반환합니다.|  
|[toFixed 메서드](../../javascript/reference/tofixed-method-number-javascript.md)|고정 소수점 표기법으로 숫자를 나타내는 문자열을 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-number.md)|현재 로캘에 따라 문자열로 변환된 개체를 반환합니다.|  
|[toPrecision 메서드](../../javascript/reference/toprecision-method-number-javascript.md)|지수 또는 고정 소수점 표기법으로 표시되고 지정한 자릿수를 가진 숫자를 포함하는 문자열을 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-object-javascript.md)|개체를 나타내는 문자열을 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-object-javascript.md)|지정된 개체의 기본 값을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 개체](../../javascript/reference/javascript-objects.md)   
 [Math 개체](../../javascript/reference/math-object-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)