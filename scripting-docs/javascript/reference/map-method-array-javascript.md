---
title: "map 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- map method [JavaScript]
- arrays [JavaScript], map method
ms.assetid: 500dc4f8-d73d-4a28-a5b8-c9bd5674ea36
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 609d9c88000a7a30fe8edc03b52df032f7d19ba9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="map-method-array-javascript"></a>map 메서드(Array)(JavaScript)
배열의 각 요소에 대해 정의된 호출 함수를 호출하고 결과가 포함된 배열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.map(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 배열 개체입니다.|  
|`callbackfn`|필수 요소. 최대 3개의 인수를 받아들이는 함수입니다. `map` 메서드는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항입니다. `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다. `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.|  
  
## <a name="return-value"></a>반환 값  
 각 요소가 연관된 원본 배열 요소에 대한 콜백 함수 반환 값인 새 배열입니다.  
  
## <a name="exceptions"></a>예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="remarks"></a>설명  
 `map` 메서드는 배열의 각 요소에 대해 한 번씩 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다. 배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `map` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
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
 배열 개체는 콜백 함수로 수정할 수 있습니다.  
  
 다음 표에서는 `map` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`map` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|---------------------------------------------|------------------------------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `map` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Define the callback function.  
function AreaOfCircle(radius) {  
    var area = Math.PI * (radius * radius);  
    return area.toFixed(0);  
}  
  
// Create an array.  
var radii = [10, 20, 30];  
  
// Get the areas from the radii.  
var areas = radii.map(AreaOfCircle);  
  
document.write(areas);  
  
// Output:  
// 314,1257,2827  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `thisArg` 키워드가 참조할 수 있는 개체를 지정하는 `this` 인수를 사용하는 방법을 보여줍니다.  
  
```JavaScript  
// Define an object that contains a divisor property and  
// a remainder function.  
var obj = {  
    divisor: 10,  
    remainder: function (value) {  
        return value % this.divisor;  
    }  
}  
  
// Create an array.  
var numbers = [6, 12, 25, 30];  
  
// Get the remainders.  
// The obj argument specifies the this value in the callback function.  
var result = numbers.map(obj.remainder, obj);  
document.write(result);  
  
// Output:  
// 6,2,5,0  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 제공되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 메서드가 콜백 함수로 사용됩니다.  
  
```JavaScript  
// Apply Math.sqrt(value) to each element in an array.  
var numbers = [9, 16];  
var result = numbers.map(Math.sqrt);  
  
document.write(result);  
// Output: 3,4  
```  
  
## <a name="example"></a>예제  
 `map` 메서드는 문자열에 적용할 수 있습니다. 다음은 이에 대한 예입니다.  
  
```JavaScript  
// Define the callback function.  
function threeChars(value, index, str) {  
    // Create a string that contains the previous, current,  
    // and next character.  
    return str.substring(index - 1, index + 2);  
}  
  
// Create a string.  
var word = "Thursday";  
  
// Apply the map method to the string.  
// Each array element in the result contains a string that  
// has the previous, current, and next character.  
// The commented out statement shows an alternative syntax.  
var result = [].map.call(word, threeChars);  
// var result = Array.prototype.map.call(word, threeChars);  
  
document.write(result);  
  
// Output:  
// Th,Thu,hur,urs,rsd,sda,day,ay  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)   
 [filter 메서드 (Array)](../../javascript/reference/filter-method-array-javascript.md)   
 [forEach 메서드 (Array)](../../javascript/reference/foreach-method-array-javascript.md)   
 [Hilo JavaScript 샘플 응용 프로그램 (Windows 스토어)](http://hilojs.codeplex.com/SourceControl/latest)