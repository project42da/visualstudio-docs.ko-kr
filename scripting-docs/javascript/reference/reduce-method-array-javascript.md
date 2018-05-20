---
title: reduce 메서드 (Array) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- callback function, reduce method [JavaScript]
- arrays [JavaScript], reduce method
- reduce method [JavaScript]
ms.assetid: 48d069e0-e083-494f-86d5-d459d2377dc5
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d99f92d90885f26b19392b476ee64ae17bd40aed
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="reduce-method-array-javascript"></a>reduce 메서드(Array)(JavaScript)
배열의 모든 요소에 대해 지정 된 콜백 함수를 호출합니다. 호출 함수의 반환 값은 누적된 결과이며, 호출 함수에 대한 다음 호출에서 인수로 제공됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.reduce(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수. 배열 개체입니다.|  
|`callbackfn`|필수. 최대 4 개의 인수를 허용 하는 함수입니다. `reduce` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`initialValue`|선택 사항입니다. 경우 `initialValue` 을 지정 누적을 시작 하는 초기 값으로 사용 됩니다. 첫 번째 호출에서 `callbackfn` 함수는 배열 값 대신 인수로 서이 값을 제공 합니다.|  
  
## <a name="return-value"></a>반환 값  
 콜백 함수에 대 한 마지막 호출에서 누적 된 결과입니다.  
  
## <a name="exceptions"></a>예외  
 A `TypeError` 경우 예외가 throw 되는 다음 조건 중 하나에 해당 합니다.  
  
-   `callbackfn` 인수가 함수 개체가 아닌 합니다.  
  
-   배열에 요소가 없는 및 `initialValue` 제공 되지 않았습니다.  
  
## <a name="remarks"></a>설명  
 경우는 `initialValue` 제공 되는 `reduce` 메서드 호출의 `callbackfn` 오름차순 인덱스 순서로 배열에 있는 각 요소에 대해 한 번씩 작동 합니다. 경우는 `initialValue` 를 제공 하지 않으면는 `reduce` 메서드 호출의 `callbackfn` 두 번째 요소부터 각 요소에 대해 함수입니다.  
  
 콜백 함수의 반환 값으로 제공 되는 `accumulator` 다음 콜백 함수 호출의 인수입니다. 콜백 함수에 대 한 마지막 호출의 반환 값은의 반환 값은 `reduce` 메서드.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
> [!NOTE]
>  [reduceRight 메서드 (Array)](../../javascript/reference/reduceright-method-array-javascript.md) 내림차순 인덱스 순서로 요소를 처리 합니다.  
  
## <a name="callback-function-syntax"></a>호출 함수 구문  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(accumulator, currentValue, currentIndex, array1)`  
  
 최대 4 개의 매개 변수를 사용 하 여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|호출 인수|정의|  
|-----------------------|----------------|  
|`accumulator`|콜백 함수에 대 한 이전 호출에서 값입니다. 경우는 `initialValue` 에 제공 되는 `reduce` 메서드를는 `accumulator` 은 `initialValue` 처음으로 함수를 호출 합니다.|  
|`currentValue`|현재 배열 요소의 값입니다.|  
|`currentIndex`|현재 배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 배열 개체입니다.|  
  
## <a name="first-call-to-the-callback-function"></a>첫 번째 콜백 함수 호출  
 콜백 함수를 호출 하는 처음으로 인수로 제공 된 값이 있는지 여부에 종속 된 `reduce` 메서드에는 `initialValue` 인수입니다.  
  
 경우는 `initialValue` reduce 메서드에 제공 됩니다.  
  
-   `accumulator` 인수가 `initialValue`인 경우  
  
-   `currentValue` 인수는 배열에 있는 첫 번째 요소 값입니다.  
  
 경우는 `initialValue` 제공 되지 않습니다.  
  
-   `accumulator` 인수는 배열에 있는 첫 번째 요소 값입니다.  
  
-   `currentValue` 인수는 배열에 있는 두 번째 요소 값입니다.  
  
## <a name="modifying-the-array-object"></a>배열 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `reduce` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`reduce` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|------------------------------------------------|------------------------------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## <a name="example"></a>예제  
 배열 값으로 값을 구분 하는 문자열에 연결 하 여 다음 예제에서는 "::". 초기 값을 제공 되기 때문에 `reduce` 메서드를 콜백 함수에 대 한 첫 번째 호출 자기 "abc"는 `accumulator` 인수와 "def"로 `currentValue` 인수입니다.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (accumulator, currentValue) {  
    return accumulator + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduce method, which calls the callback function  
// for each array element.  
var result = elements.reduce(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  abc::def::123::456  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 처리 된 후 배열 값을 추가 합니다. `reduce` 초기 값이 0 인 메서드 호출 됩니다.  
  
```JavaScript  
// Define the callback function.  
function addRounded (accumulator, currentValue) {  
    return accumulator + Math.round(currentValue);  
    }  
  
// Create an array.  
var numbers = [10.9, 15.4, 0.5];  
  
// Call the reduce method, starting with an initial value of 0.  
var result = numbers.reduce(addRounded, 0);  
  
document.write (result);  
// Output: 27  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 값을 추가합니다. `currentIndex` 및 `array1` 매개 변수는 콜백 함수에 사용 됩니다.  
  
```JavaScript  
function addDigitValue(accumulator, currentDigit, currentIndex, array) {  
    var exponent = (array.length - 1) - currentIndex;  
    var digitValue = currentDigit * Math.pow(10, exponent);  
    return accumulator + digitValue;  
    }  
  
var digits = [4, 1, 2, 5];  
  
// Determine an integer that is computed from values in the array.  
var result = digits.reduce(addDigitValue, 0);  
  
document.write (result);  
// Output: 4125  
```  
  
## <a name="example"></a>예제  
 다음 예제에는 1에서 다른 배열에서 10 사이의 값만 포함 하는 배열을 가져옵니다. 에 제공 된 초기 값은 `reduce` 메서드는 빈 배열입니다.  
  
```JavaScript  
function Process(accumulatedArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = accumulatedArray.concat(currentValue);  
    else  
        nextArray = accumulatedArray;  
  
    // If this is not the last call by the reduce method,  
    // the returned array is accumulatedArray on the next call.  
    // If this is the last call by the reduce method, the  
    // returned array is the return value of the reduce method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduce method, starting with an initial empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduce(Process, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
// result array=1,6,3  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [reduceRight 메서드(Array)](../../javascript/reference/reduceright-method-array-javascript.md)
