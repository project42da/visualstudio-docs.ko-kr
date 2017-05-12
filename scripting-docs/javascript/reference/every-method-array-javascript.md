---
title: "every 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], every 메서드"
  - "every 메서드"
ms.assetid: dc4ee2f8-fb9e-4c9f-af5a-fe836e40ddd1
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# every 메서드(Array)(JavaScript)
배열의 모든 멤버가 지정한 테스트를 충족하는지 여부를 확인합니다.  
  
## 구문  
  
```  
  
array1.every(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`callbackfn`|필수 요소.  최대 3개까지 인수를 허용하는 함수입니다.  `every` 메서드는 `callbackfn`에서 `false`를 반환하거나 배열이 끝날 때까지 `array1`의 각 요소에 대해 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항입니다.  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this`로 사용됩니다.|  
  
## 반환 값  
 `callbackfn` 함수가 모든 배열 요소에 대해 `true`를 반환하면 `true`이고, 그렇지 않으면 `false`입니다.  배열에 요소가 없으면 `every` 메서드에서 `true`를 반환합니다.  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 `every` 메서드는 `callbackfn` 함수가 `false`를 반환할 때까지 인덱스 오름차순으로 각 배열 요소에 대해 `callbackfn` 함수를 한 번 호출합니다.  `callbackfn`에서 `false`를 반환하게 하는 요소가 있으면 `every` 메서드는 즉시 `false`를 반환합니다.  그렇지 않으면 `every` 메서드는 `true`를 반환합니다.  
  
 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `every` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
> [!NOTE]
>  [some 메서드\(Array\)](../../javascript/reference/some-method-array-javascript.md)를 사용하여 콜백 함수가 배열의 임의 요소에 대해 `true`를 반환하는지 여부를 검사할 수 있습니다.  
  
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
  
 다음 표에서는 `every` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`every` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|----------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 `every` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
// Define the callback function.  
function CheckIfEven(value, index, ar) {  
    document.write(value + " ");  
  
    if (value % 2 == 0)  
        return true;  
    else  
        return false;  
}  
  
// Create an array.  
var numbers = [2, 4, 5, 6, 8];  
  
// Check whether the callback function returns true for all of the  
// array values.  
if (numbers.every(CheckIfEven))  
    document.write("All are even.");  
else  
    document.write("Some are not even.");  
  
// Output:  
// 2 4 5 Some are not even.  
```  
  
## 예제  
 다음 예제에서는 `this` 키워드가 참조할 수 있는 개체를 지정하는 `thisArg` 인수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// Create a function that returns true if the value is  
// numeric and within range.  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [10, 15, 19];  
  
// Check whether the callback function returns true for  
// all of the array values.  
// The obj argument enables use of the this value  
// within the callback function.  
  
var obj = { minimum: 10, maximum: 20 }  
  
if (numbers.every(checkNumericRange, obj))  
    document.write ("All are within range.");  
else  
    document.write ("Some are not within range.");  
  
// Output:  
//   All are within range.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [some 메서드\(Array\)](../../javascript/reference/some-method-array-javascript.md)   
 [filter 메서드\(Array\)](../../javascript/reference/filter-method-array-javascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)