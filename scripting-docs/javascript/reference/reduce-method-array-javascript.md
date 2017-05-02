---
title: "reduce 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], reduce 메서드"
  - "콜백 함수, reduce 메서드[JavaScript]"
  - "reduce 메서드[JavaScript]"
ms.assetid: 48d069e0-e083-494f-86d5-d459d2377dc5
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# reduce 메서드(Array)(JavaScript)
배열의 모든 요소에 대해 지정된 콜백을 호출합니다.  콜백 함수의 반환 값은 결과에 누적되며 다음에 콜백 함수를 호출할 때 인수로 제공됩니다.  
  
## 구문  
  
```  
  
array1.reduce(callbackfn[, initialValue])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`callbackfn`|필수 요소.  최대 4개까지 인수를 허용하는 함수입니다.  `reduce` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`initialValue`|선택 사항입니다.  `initialValue`가 지정된 경우 누적을 시작하는 초기 값으로 사용됩니다.  `callbackfn` 함수에 대한 첫 번째 호출은 이 값을 배열 값 대신 인수로 제공합니다.|  
  
## 반환 값  
 콜백 함수에 대한 마지막 호출로부터 누적된 결과입니다.  
  
## 예외  
 `TypeError` 예외는 다음 조건 중 하나가 true인 경우 throw됩니다.  
  
-   `callbackfn` 인수는 함수 개체가 아닌 경우  
  
-   배열에 요소가 포함되지 않고 `initialValue`가 제공되지 않은 경우  
  
## 설명  
 `initialValue`가 제공된 경우 `reduce` 메서드가 배열에 있는 각 요소에 대해 한 번씩 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다.  `initialValue`가 제공되지 않은 경우 `reduce` 메서드가 두 번째 요소부터 시작하여 각 요소에 대해 `callbackfn` 함수를 호출합니다.  
  
 콜백 함수의 반환 값은 콜백 함수에 대한 다음 호출의 `previousValue` 인수로 제공됩니다.  콜백 함수에 대한 마지막 호출의 반환 값은 `reduce` 메서드의 반환 값입니다.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
> [!NOTE]
>  [reduceRight 메서드\(Array\)](../../javascript/reference/reduceright-method-array-javascript.md)는 내림차순 인덱스 순서로 요소를 처리합니다.  
  
## 콜백 함수 구문  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(previousValue, currentValue, currentIndex, array1)`  
  
 매개 변수를 최대 4개까지 사용하여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`previousValue`|콜백 함수에 대한 이전 호출로부터 얻은 값입니다.  `initialValue`가 `reduce` 메서드에 제공된 경우 `previousValue`는 함수를 처음 호출할 때의 `initialValue`입니다.|  
|`currentValue`|현재 배열 요소의 값입니다.|  
|`currentIndex`|현재 배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 Array 개체입니다.|  
  
## 콜백 함수에 대한 첫 번째 호출  
 콜백 함수를 처음 호출할 때 인수로 제공되는 값은 `reduce` 메서드에 `initialValue` 인수가 포함되었는지 여부에 따라 달라집니다.  
  
 `initialValue`가 reduce 메서드에 제공된 경우:  
  
-   `previousValue` 인수가 `initialValue`입니다.  
  
-   `currentValue` 인수가 배열에 있는 첫 번째 요소의 값입니다.  
  
 `initialValue`가 제공되지 않은 경우:  
  
-   `previousValue` 인수가 배열에 있는 첫 번째 요소의 값입니다.  
  
-   `currentValue` 인수가 배열에 있는 두 번째 요소의 값입니다.  
  
## Array 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `reduce` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`reduce` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|-----------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 값을 "::"으로 구분하여 배열 값을 문자열로 연결하는 것을 보여 줍니다.  `reduce` 메서드에 초기 값이 제공되지 않았기 때문에 콜백 함수에 대한 첫 번째 호출은 `previousValue` 인수로 "abc"를 사용하고 `currentValue` 인수로 "def"를 사용합니다.  
  
```javascript  
// Define the callback function.  
function appendCurrent (previousValue, currentValue) {  
    return previousValue + "::" + currentValue;  
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
  
## 예제  
 다음 예제에서는 배열 값을 반올림한 후 배열 값을 더합니다.  `reduce` 메서드는 초기 값 0으로 호출됩니다.  
  
```javascript  
// Define the callback function.  
function addRounded (previousValue, currentValue) {  
    return previousValue + Math.round(currentValue);  
    }  
  
// Create an array.  
var numbers = [10.9, 15.4, 0.5];  
  
// Call the reduce method, starting with an initial value of 0.  
var result = numbers.reduce(addRounded, 0);  
  
document.write (result);  
// Output: 27  
```  
  
## 예제  
 다음 예제에서는 배열의 값을 더합니다.  `currentIndex` 및`array1` 매개 변수는 콜백 함수에 사용됩니다.  
  
```javascript  
function addDigitValue(previousValue, currentDigit, currentIndex, array) {  
    var exponent = (array.length - 1) - currentIndex;  
    var digitValue = currentDigit * Math.pow(10, exponent);  
    return previousValue + digitValue;  
    }  
  
var digits = [4, 1, 2, 5];  
  
// Determine an integer that is computed from values in the array.  
var result = digits.reduce(addDigitValue, 0);  
  
document.write (result);  
// Output: 4125  
```  
  
## 예제  
 다음 예제에서는 다른 배열에서 1~10 사이의 값만 포함하는 배열을 가져옵니다.  `reduce` 메서드에 제공된 초기 값은 빈 배열입니다.  
  
```javascript  
function Process(previousArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = previousArray.concat(currentValue);  
    else  
        nextArray = previousArray;  
  
    // If this is not the last call by the reduce method,  
    // the returned array is previousArray on the next call.  
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
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [reduceRight 메서드\(Array\)](../../javascript/reference/reduceright-method-array-javascript.md)