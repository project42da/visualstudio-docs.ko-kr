---
title: "reduceRight 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], reduceRight method
- reduceRight method [JavaScript]
ms.assetid: 85963761-da11-407c-8bce-278c930e61bd
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d7fd2794157eadacefa7404f9333c51aed9425c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="reduceright-method-array-javascript"></a>reduceRight 메서드(Array)(JavaScript)
내림차순 배열의 모든 요소에 대해 지정 된 콜백 함수를 호출 합니다. 호출 함수의 반환 값은 누적된 결과이며, 호출 함수에 대한 다음 호출에서 인수로 제공됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.reduceRight(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 배열 개체입니다.|  
|`callbackfn`|필수 요소. 최대 4 개의 인수를 허용 하는 함수입니다. `reduceRight` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`initialValue`|선택 사항입니다. 경우 `initialValue` 을 지정 누적을 시작 하는 초기 값으로 사용 됩니다. 첫 번째 호출에서 `callbackfn` 함수는 배열 값 대신 인수로 서이 값을 제공 합니다.|  
  
## <a name="return-value"></a>반환 값  
 콜백 함수에 대 한 마지막 호출에서 누적 된 결과 포함 하는 개체입니다.  
  
## <a name="exceptions"></a>예외  
 A `TypeError` 경우 예외가 throw 되는 다음 조건 중 하나에 해당 합니다.  
  
-   `callbackfn` 인수가 함수 개체가 아닌 합니다.  
  
-   배열에 요소가 없는 및 `initialValue` 제공 되지 않았습니다.  
  
## <a name="remarks"></a>설명  
 경우는 `initialValue` 제공 되는 `reduceRight` 메서드 호출은 `callbackfn` 인덱스 내림차순 배열의 각 요소에 대해 한 번씩 작동 합니다. 없는 경우 `initialValue` 제공 됩니다는 `reduceRight` 메서드 호출에서 `callbackfn` 마지막에서 두 번째 요소 인덱스의 내림차순으로 시작 하는 각 요소에 대해 함수입니다.  
  
 콜백 함수의 반환 값으로 제공 되는 `previousValue` 다음 콜백 함수 호출의 인수입니다. 콜백 함수에 대 한 마지막 호출의 반환 값은의 반환 값은 `reduceRight` 메서드.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 사용 하 여 오름차순 인덱스 순서로 결과 누적 하 여 [reduce 메서드 (Array)](../../javascript/reference/reduce-method-array-javascript.md)합니다.  
  
## <a name="callback-function-syntax"></a>호출 함수 구문  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(previousValue, currentValue, currentIndex, array1)`  
  
 최대 4 개의 매개 변수를 사용 하 여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 인수|정의|  
|-----------------------|----------------|  
|`previousValue`|콜백 함수에 대 한 이전 호출에서 값입니다. 경우는 `initialValue` 에 제공 되는 `reduceRight` 메서드를는 `previousValue` 은 `initialValue` 처음으로 함수를 호출 합니다.|  
|`currentValue`|현재 배열 요소의 값입니다.|  
|`currentIndex`|현재 배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 배열 개체입니다.|  
  
## <a name="first-call-to-the-callback-function"></a>첫 번째 콜백 함수 호출  
 콜백 함수를 호출 하는 처음으로 인수로 제공 된 값이 있는지 여부에 종속 된 `reduceRight` 메서드에는 `initialValue` 인수입니다.  
  
 경우는 `initialValue` 에 제공 되는 `reduceRight` 메서드:  
  
-   `previousValue` 인수가 `initialValue`인 경우  
  
-   `currentValue` 인수는 배열에 있는 마지막 요소의 값입니다.  
  
 경우는 `initialValue` 제공 되지 않습니다.  
  
-   `previousValue` 인수는 배열에 있는 마지막 요소의 값입니다.  
  
-   `currentValue` 인수는 배열에 있는 마지막에서 두 번째 요소 값입니다.  
  
## <a name="modifying-the-array-object"></a>배열 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `reduceRight` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`reduceRight` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|-----------------------------------------------------|------------------------------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## <a name="example"></a>예제  
 배열 값으로 값을 구분 하는 문자열에 연결 하 여 다음 예제에서는 "::". 초기 값을 제공 되기 때문에 `reduceRight` 메서드가, 콜백 함수에 대 한 첫 번째 호출으로 456는 `previousValue` 인수와 123으로 `currentValue` 인수입니다.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (previousValue, currentValue) {  
    return previousValue + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduceRight method, which calls the callback function  
// for each array element, in descending index order.  
var result = elements.reduceRight(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  456::123::def::abc  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열 요소의 제곱의 합을 찾습니다. `reduceRight` 초기 값이 0 인 메서드 호출 됩니다.  
  
```JavaScript  
// Define the callback function.  
function Process(previousValue, currentValue, index, array) {  
    // Add the previous value to the current value squared.  
    var nextValue = previousValue + (currentValue * currentValue);  
  
    // If this is not the last call by the reduceRight method,  
    // the return value is previousValue on the next call.  
    // If this is the last call by the reduceRight method, the  
    // return value is the return value of the reduceRight method.  
    return nextValue;  
}  
  
// Create an array.  
var numbers = [3, 4, 5];  
  
// Call the reduceRight method with an initial value of 0.  
var sumOfSquares = numbers.reduceRight(Process, 0);  
  
document.write("sum of squares=" + sumOfSquares);  
  
// Output:  
//  sum of squares=50  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 해당 값은 1과 10 사이의 배열의 해당 요소를 가져옵니다. 에 제공 된 초기 값은 `reduceRight` 메서드는 빈 배열입니다.  
  
```JavaScript  
function Process2(previousArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = previousArray.concat(currentValue);  
    else  
        nextArray = previousArray;  
  
    // If this is not the last call by the reduceRight method,  
    // the returned array is previousArray on the next call.  
    // If this is the last call by the reduceRight method, the  
    // returned array is the return value of the reduceRight method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduceRight method, starting with an empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduceRight(Process2, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
//  result array=3,6,1  
```  
  
## <a name="example"></a>예제  
 `reduceRight` 메서드는 문자열에 적용할 수 있습니다. 다음 예제에서는 문자열의 문자를 반대로 하려면이 메서드를 사용 하는 방법을 보여 줍니다.  
  
```JavaScript  
// Define the callback function.  
function AppendToArray(previousValue, currentValue) {  
    return previousValue + currentValue;  
}  
  
var word = "retupmoc";  
  
// Create a string that reverses the characters of another string.  
// The commented-out statement shows an alternative syntax.  
var result = [].reduceRight.call(word, AppendToArray, "the ");  
// var result = Array.prototype.reduceRight.call(word, AppendToArray, "the ");  
  
document.write(result);  
  
// Output:  
// the computer  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [reduce 메서드(Array)](../../javascript/reference/reduce-method-array-javascript.md)