---
title: "reduceRight 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], reduceRight 메서드"
  - "reduceRight 메서드[JavaScript]"
ms.assetid: 85963761-da11-407c-8bce-278c930e61bd
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# reduceRight 메서드(Array)(JavaScript)
배열의 모든 요소에 대해 지정된 콜백을 내림차순으로 호출합니다.  콜백 함수의 반환 값은 결과에 누적되며 다음에 콜백 함수를 호출할 때 인수로 제공됩니다.  
  
## 구문  
  
```  
  
array1.reduceRight(callbackfn[, initialValue])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`callbackfn`|필수 요소.  최대 4개까지 인수를 허용하는 함수입니다.  `reduceRight` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`initialValue`|선택 사항입니다.  `initialValue`가 지정된 경우 누적을 시작하는 초기 값으로 사용됩니다.  `callbackfn` 함수에 대한 첫 번째 호출은 이 값을 배열 값 대신 인수로 제공합니다.|  
  
## 반환 값  
 콜백 함수에 대한 마지막 호출로부터 누적된 결과를 포함하는 개체입니다.  
  
## 예외  
 `TypeError` 예외는 다음 조건 중 하나가 true인 경우 throw됩니다.  
  
-   `callbackfn` 인수는 함수 개체가 아닌 경우  
  
-   배열에 요소가 포함되지 않고 `initialValue`가 제공되지 않은 경우  
  
## 설명  
 `initialValue`가 제공된 경우 `reduceRight` 메서드가 배열의 각 요소에 대해 한 번씩 내림차순 인덱스 순서로 `callbackfn` 함수를 호출합니다.  `initialValue`가 제공되지 않은 경우 `reduceRight` 메서드가 마지막에서 두 번째 요소부터 시작하여 각 요소에 대해 `callbackfn` 함수를 내림차순 인덱스 순서로 호출합니다.  
  
 콜백 함수의 반환 값은 콜백 함수에 대한 다음 호출의 `previousValue` 인수로 제공됩니다.  콜백 함수에 대한 마지막 호출의 반환 값은 `reduceRight` 메서드의 반환 값입니다.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 결과를 오름차순 인덱스 순서로 누적하려면 [reduce 메서드\(Array\)](../../javascript/reference/reduce-method-array-javascript.md)를 사용합니다.  
  
## 콜백 함수 구문  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(previousValue, currentValue, currentIndex, array1)`  
  
 매개 변수를 최대 4개까지 사용하여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`previousValue`|콜백 함수에 대한 이전 호출로부터 얻은 값입니다.  `initialValue`가 `reduceRight` 메서드에 제공된 경우 `previousValue`는 함수를 처음 호출할 때의 `initialValue`입니다.|  
|`currentValue`|현재 배열 요소의 값입니다.|  
|`currentIndex`|현재 배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 Array 개체입니다.|  
  
## 콜백 함수에 대한 첫 번째 호출  
 콜백 함수를 처음 호출할 때 인수로 제공되는 값은 `reduceRight` 메서드에 `initialValue` 인수가 포함되었는지 여부에 따라 달라집니다.  
  
 `initialValue`가 `reduceRight` 메서드에 제공된 경우:  
  
-   `previousValue` 인수가 `initialValue`입니다.  
  
-   `currentValue` 인수가 배열에 있는 마지막 요소의 값입니다.  
  
 `initialValue`가 제공되지 않은 경우:  
  
-   `previousValue` 인수가 배열에 있는 마지막 요소의 값입니다.  
  
-   `currentValue` 인수가 배열에 있는 마지막에서 두 번째 요소의 값입니다.  
  
## Array 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `reduceRight` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`reduceRight` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|----------------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 값을 "::"으로 구분하여 배열 값을 문자열로 연결하는 것을 보여 줍니다.  `reduceRight` 메서드에 초기 값이 제공되지 않았기 때문에 콜백 함수에 대한 첫 번째 호출은 `previousValue` 인수로 456을 사용하고 `currentValue` 인수로 123을 사용합니다.  
  
```javascript  
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
  
## 예제  
 다음 예제에서는 배열 요소의 제곱합 합계를 찾습니다.  `reduceRight` 메서드는 초기 값 0으로 호출됩니다.  
  
```javascript  
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
  
## 예제  
 다음 예제에서는 값이 1~10 사이인 배열의 요소를 가져옵니다.  `reduceRight` 메서드에 제공된 초기 값은 빈 배열입니다.  
  
```javascript  
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
  
## 예제  
 `reduceRight` 메서드는 문자열에 적용할 수 있습니다.  다음 예제에서는 이 메서드를 사용하여 문자열의 문자를 역순으로 하는 방법을 보여 줍니다.  
  
```javascript  
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
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [reduce 메서드\(Array\)](../../javascript/reference/reduce-method-array-javascript.md)