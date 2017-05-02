---
title: "some 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], some 메서드"
  - "some 메서드[JavaScript]"
ms.assetid: 7b6822f9-c406-4f4e-bfec-a93459745992
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# some 메서드(Array)(JavaScript)
배열의 모든 요소에 대해 지정된 콜백 함수가 `true`를 반환하는지 여부를 결정합니다.  
  
## 구문  
  
```  
  
array1.some(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`callbackfn`|필수 요소.  최대 3개까지 인수를 허용하는 함수입니다.  `some` 메서드는 `callbackfn`에서 `true`를 반환하거나 배열이 끝날 때까지 `array1`의 각 요소에 대해 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항입니다.  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this`로 사용됩니다.|  
  
## 반환 값  
 `callbackfn` 함수가 배열 요소에 대해 `true`를 반환할 경우 `true`이고 그렇지 않으면 `false`입니다.  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 `callbackfn` 함수가 `true`를 반환할 때까지 `some` 메서드는 각 배열 요소에 대해 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다.  `callbackfn`에서 `true`를 반환하게 하는 요소가 있으면 `some` 메서드는 즉시 `true`를 반환합니다.  콜백이 모든 요소에 대해 `true`를 반환하지 않으면 `some` 메서드가 `false`를 반환합니다.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `some` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
> [!NOTE]
>  [every 메서드\(Array\)](../../javascript/reference/every-method-array-javascript.md)를 사용하면 배열의 모든 요소에 대해 콜백 함수가 `true`를 반환하는지 여부를 확인할 수 있습니다.  
  
## 콜백 함수 구문  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, array1)`  
  
 매개 변수를 최대 3개까지 사용하여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 매개 변수|정의|  
|--------------|--------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 Array 개체입니다.|  
  
## Array 개체 수정  
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `some` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`some` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|---------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 `some` 메서드로 배열의 모든 요소가 짝수인지 확인합니다.  
  
```javascript  
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
  
## 예제  
 다음 예제에서는 `this` 키워드가 참조할 수 있는 개체를 지정하는 `thisArg` 매개 변수를 사용하는 방법을 보여 줍니다.  이 매개 변수는 배열의 모든 숫자가 전달된 개체에서 제공된 범위 바깥에 있는지 확인합니다.  
  
```javascript  
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
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [every 메서드\(Array\)](../../javascript/reference/every-method-array-javascript.md)   
 [filter 메서드\(Array\)](../../javascript/reference/filter-method-array-javascript.md)   
 [map 메서드\(Array\)](../../javascript/reference/map-method-array-javascript.md)