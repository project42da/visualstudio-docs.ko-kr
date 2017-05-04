---
title: "filter 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], filter 메서드"
  - "filter 메서드[JavaScript]"
ms.assetid: 1d260370-9e6e-43fc-870f-2d35850db7ee
caps.latest.revision: 32
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 32
---
# filter 메서드(Array)(JavaScript)
콜백 함수에 지정된 조건을 충족하는 배열의 요소를 반환합니다.  
  
## 구문  
  
```  
  
array1.filter(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`callbackfn`|필수 요소.  최대 3개까지 인수를 허용하는 함수입니다.  `filter` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항입니다.  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this`로 사용됩니다.|  
  
## 반환 값  
 콜백 함수가 `true`를 반환하는 모든 값을 포함하는 새 배열입니다.  콜백 함수가 `array1`의 모든 요소에 대해 `false`를 반환하는 경우 새 배열의 길이는 0입니다.  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 `filter` 메서드는 배열의 각 요소에 대해 한 번씩 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다.  배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `filter` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
## 콜백 함수 구문  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, array1)`  
  
 매개 변수를 최대 3개까지 사용하여 콜백 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 Array 개체입니다.|  
  
## Array 개체 수정  
 `filter` 메서드는 원래 배열을 직접 수정하지 않지만 콜백 함수는 수정할 수 있습니다.  다음 표에서는 `filter` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`filter` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|-----------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 `filter` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
// Define a callback function.  
function CheckIfPrime(value, index, ar) {  
    high = Math.floor(Math.sqrt(value)) + 1;  
  
    for (var div = 2; div <= high; div++) {  
        if (value % div == 0) {  
            return false;  
        }  
    }   
    return true;  
}  
  
// Create the original array.  
var numbers = [31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53];  
  
// Get the prime numbers that are in the original array.   
var primes = numbers.filter(CheckIfPrime);  
  
document.write(primes);  
// Output: 31,37,41,43,47,53  
```  
  
## 예제  
 다음 예제에서는 `callbackfn` 인수에 콜백 함수의 코드가 포함되어 있습니다.  
  
```javascript  
// Create the original array.  
var arr = [5, "element", 10, "the", true];  
  
// Create an array that contains the string  
// values that are in the original array.  
var result = arr.filter(  
    function (value) {  
        return (typeof value === 'string');  
    }  
);  
  
document.write(result);  
// Output: element, the  
```  
  
## 예제  
 다음 예제에서는 `window` DOM 개체의 "css" 문자로 시작되는 속성 이름을 표시합니다.  
  
```javascript  
var filteredNames = Object.getOwnPropertyNames(window).filter(IsC);  
  
    for (i in filteredNames)  
        document.write(filteredNames[i] + "<br/>");  
  
// Check whether the string starts with "css".  
function IsC(value) {  
    var firstChar = value.substr(0, 3);  
    if (firstChar.toLowerCase() == "css")  
        return true;  
    else  
        return false;  
    }  
  
// Output:  
// CSSRule  
// CSSFontFaceRule  
// CSSImportRule  
// CSSMediaRule  
// CSSNamespaceRule  
// CSSPageRule  
// CSSRuleList  
// CSSStyleDeclaration  
// CSSStyleRule  
// CSSStyleSheet  
  
```  
  
## 예제  
 다음 예제에서는 `this` 키워드가 참조할 수 있는 개체를 지정하는 `thisArg` 인수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
var numbers = [6, 12, "15", 16, "the", -12];  
  
// The obj argument enables use of the this value  
// within the callback function.  
var obj = { minimum: 10, maximum: 20 }  
  
var result = numbers.filter(checkNumericRange, obj);  
  
document.write(result);  
// Output: 12,16  
  
```  
  
## 예제  
 `filter` 메서드는 배열 대신 문자열에 적용할 수 있습니다.  다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
```javascript  
// Define a callback function that returns true  
// if the current array element follows a space  
// or is the first character.  
function CheckValue(value, index, ar) {  
    if (index == 0)  
        return true;  
    else  
        return ar[index - 1] === " ";  
}  
  
// Create a string.  
var sentence = "The quick brown fox jumps over the lazy dog.";   
  
// Create an array that contains all characters that follow a space.  
var subset = [].filter.call(sentence, CheckValue);   
  
// You can use this alternative syntax.  
//var subset = Array.prototype.filter.call(sentence, CheckValue);  
  
document.write(subset);  
// Output: T,q,b,f,j,o,t,l,d  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)   
 [map 메서드\(Array\)](../../javascript/reference/map-method-array-javascript.md)   
 [forEach 메서드\(Array\)](../../javascript/reference/foreach-method-array-javascript.md)