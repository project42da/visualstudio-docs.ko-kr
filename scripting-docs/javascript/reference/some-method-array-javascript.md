---
title: "일부 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], some method
- some method [JavaScript]
ms.assetid: 7b6822f9-c406-4f4e-bfec-a93459745992
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba3f855c61daac511bcf7aca6b47f643dda93313
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="some-method-array-javascript"></a>some 메서드(Array)(JavaScript)
지정 된 콜백 함수 반환 하는지 여부를 결정 `true` 배열의 모든 요소에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.some(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 배열 개체입니다.|  
|`callbackfn`|필수 요소. 최대 3개의 인수를 받아들이는 함수입니다. `some` 메서드 호출의 `callbackfn` 의 각 요소에 대 한 함수 `array1` 될 때까지 `callbackfn` 반환 `true`, 또는 배열의 끝까지 합니다.|  
|`thisArg`|선택적 요소. `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다. `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.|  
  
## <a name="return-value"></a>반환 값  
 `true`경우는 `callbackfn` 함수에서 반환 `true` 모든 배열 요소의; 그렇지 않으면 `false`합니다.  
  
## <a name="exceptions"></a>예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="remarks"></a>설명  
 `some` 메서드 호출의 `callbackfn` 될 때까지 오름차순 인덱스 순서로 각 배열 요소에 대해 함수는 `callbackfn` 함수에서 반환 `true`합니다. 하는 경우 발생 하는 요소 `callbackfn` 반환할 `true` 발견 되는 `some` 메서드가 즉시 반환 `true`합니다. 콜백 반환 하지 않는 경우 `true` 모든 요소에는 `some` 메서드 반환 `false`합니다.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `some` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
> [!NOTE]
>  사용할 수는 [every 메서드 (Array)](../../javascript/reference/every-method-array-javascript.md) 콜백 함수 반환 하는지 여부를 확인 하려면 `true` 배열의 모든 요소에 대 한 합니다.  
  
## <a name="callback-function-syntax"></a>호출 함수 구문  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, array1)`  
  
 최대 3 개의 매개 변수를 사용 하 여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 매개 변수|정의|  
|------------------------|----------------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 배열 개체입니다.|  
  
## <a name="modifying-the-array-object"></a>배열 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `some` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`some` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|----------------------------------------------|------------------------------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `some` 배열에 요소가 하나라도 했는지 확인 하는 메서드는도 합니다.  
  
```JavaScript  
// The callback function.  
function CheckIfEven(value, index, ar) {  
    if (value % 2 == 0)  
        return true;  
}  
  
var numbers = [1, 15, 4, 10, 11, 22];  
  
var evens = numbers.some(CheckIfEven);  
document.write(evens);  
  
// Output:  
// true  
```  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `thisArg` 있는 개체를 지정 하는 매개 변수는 `this` 키워드가 참조할 수 있습니다. 배열에 숫자가 전달 되는 개체에서 제공 하는 범위 밖에 있는 지 여부를 확인합니다  
  
```JavaScript  
// Create a function that returns true if the value is   
// outside the range.  
var isOutsideRange = function (value) {  
    return value < this.minimum || value > this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [6, 12, 16, 22, -12];  
  
// The range object is to be the 'this' object.  
var range = { minimum: 10, maximum: 20 };  
  
document.write(numbers.some(isOutsideRange, range));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [every 메서드 (Array)](../../javascript/reference/every-method-array-javascript.md)   
 [filter 메서드 (Array)](../../javascript/reference/filter-method-array-javascript.md)   
 [map 메서드(Array)](../../javascript/reference/map-method-array-javascript.md)