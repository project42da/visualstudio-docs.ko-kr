---
title: "filter 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], filter method
- filter method [JavaScript]
ms.assetid: 1d260370-9e6e-43fc-870f-2d35850db7ee
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33a08fdba38de558dabc749a634fb9b69c52c98a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="filter-method-array-javascript"></a>filter 메서드(Array)(JavaScript)
콜백 함수에 지정 된 조건을 만족 하는 배열의 요소를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.filter(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 배열 개체입니다.|  
|`callbackfn`|필수 요소. 최대 3개의 인수를 받아들이는 함수입니다. `filter` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항입니다. `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다. `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.|  
  
## <a name="return-value"></a>반환 값  
 콜백 함수가 반환 하는 모든 값을 포함 하는 새 배열 `true`합니다. 콜백 함수가 반환 하는 경우 `false` 의 모든 요소에 대 한 `array1`, 해당 새 배열의 길이 0입니다.  
  
## <a name="exceptions"></a>예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="remarks"></a>설명  
 `filter` 메서드는 배열의 각 요소에 대해 한 번씩 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다. 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `filter` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
## <a name="callback-function-syntax"></a>콜백 함수 구문  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, array1)`  
  
 매개 변수를 최대 3개까지 사용하여 호출 함수를 선언할 수 있습니다.  
  
 다음 표에는 콜백 함수 매개 변수가 나열되어 있습니다.  
  
|콜백 인수|정의|  
|-----------------------|----------------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 배열 개체입니다.|  
  
## <a name="modifying-the-array-object"></a>배열 개체 수정  
 `filter` 메서드는 원래 배열을 직접 수정하지 않지만 콜백 함수는 수정할 수 있습니다. 다음 표에서는 `filter` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`filter` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|------------------------------------------------|------------------------------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `filter` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 다음 예제에서는 `callbackfn` 인수에 콜백 함수의 코드가 포함되어 있습니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 다음 예제에서 "css" 문자로 시작 하는 속성의 이름을 표시는 `window` DOM 개체입니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 다음 예제에서는 `thisArg` 키워드가 참조할 수 있는 개체를 지정하는 `this` 인수를 사용하는 방법을 보여줍니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 `filter` 배열 대신 문자열에 메서드를 적용할 수 있습니다. 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)   
 [map 메서드 (Array)](../../javascript/reference/map-method-array-javascript.md)   
 [forEach 메서드(Array)](../../javascript/reference/foreach-method-array-javascript.md)