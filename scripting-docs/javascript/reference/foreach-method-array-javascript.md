---
title: "forEach 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], forEach 메서드"
  - "콜백 함수, forEach 메서드[JavaScript]"
  - "forEach 메서드[JavaScript]"
ms.assetid: bd188034-a62b-4cbd-99c8-46d70dd6823d
caps.latest.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 28
---
# forEach 메서드(Array)(JavaScript)
배열의 각 요소에 대해 지정된 작업을 수행합니다.  
  
## 구문  
  
```  
  
array1.forEach(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수입니다.  배열 개체입니다.|  
|`callbackfn`|필수입니다.  최대 3개의 인수를 받아들이는 함수입니다.  `forEach`는 배열에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.|  
|`thisArg`|선택 사항  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.|  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## 설명  
 `forEach` 메서드는 배열에 있는 각 요소에 대해 한 번씩 오름차순 인덱스 순서로 `callbackfn` 함수를 호출합니다.  배열의 누락된 요소에 대해 콜백 함수를 호출하지 않습니다.  
  
 배열 개체 외에도 `forEach` 메서드를 사용하면 `length` 속성을 포함하는 개체와 숫자로 인덱싱된 속성 이름을 포함하는 모든 개체에서 사용할 수 있습니다.  
  
## 콜백 함수 구문  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, array1)`  
  
 매개 변수를 최대 3개까지 사용하여 콜백 함수를 선언할 수 있습니다.  
  
 콜백 함수 매개 변수는 다음과 같습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`array1`|요소가 포함된 배열 개체입니다.|  
  
## 배열 개체 수정  
 `forEach` 메서드는 원래 배열을 직접 수정하지 않지만 콜백 함수는 수정할 수 있습니다.  다음 표에서는 `forEach` 메서드가 시작된 후 배열 개체를 수정한 결과를 보여 줍니다.  
  
|`forEach` 메서드가 시작된 후의 조건|콜백 함수에 전달된 요소|  
|------------------------------|-------------------|  
|요소는 배열의 원래 길이를 벗어나서 추가됩니다.|아니요.|  
|요소는 배열의 누락된 요소를 채우도록 추가됩니다.|예, 해당 인덱스가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 변경되었습니다.|예, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
|요소가 배열에서 삭제됩니다.|아니요, 해당 요소가 콜백 함수에 아직 전달되지 않은 경우 그렇습니다.|  
  
## 예제  
 다음 예제에서는 `forEach` 메서드를 사용하는 방법을 보여줍니다.  
  
```javascript  
// Define the callback function.  
function ShowResults(value, index, ar) {  
    document.write("value: " + value);  
    document.write(" index: " + index);  
    document.write("<br />");  
}  
  
// Create an array.  
var letters = ['ab', 'cd', 'ef'];  
  
// Call the ShowResults callback function for each  
// array element.  
letters.forEach(ShowResults);  
  
// Output:  
//  value: ab index: 0   
//  value: cd index: 1   
//  value: ef index: 2   
```  
  
## 예제  
 다음 예제에서는 `callbackfn` 인수에 콜백 함수의 코드가 포함되어 있습니다.  
  
```javascript  
// Create an array.  
var numbers = [10, 11, 12];  
  
// Call the addNumber callback function for each array element.  
var sum = 0;  
numbers.forEach(  
    function addNumber(value) { sum += value; }  
);  
  
document.write(sum);  
// Output: 33  
  
```  
  
## 예제  
 다음 예제에서는 `this` 키워드로 참조할 수 있는 개체를 지정하는 `thisArg` 인수를 사용하는 방법을 보여줍니다.  
  
```javascript  
// Define the object that contains the callback function.  
var obj = {  
    showResults: function(value, index) {  
        // Call calcSquare by using the this value.  
        var squared = this.calcSquare(value);  
  
        document.write("value: " + value);  
        document.write(" index: " + index);  
        document.write(" squared: " + squared);  
        document.write("<br />");  
    },  
    calcSquare: function(x) { return x * x }  
};  
  
// Define an array.  
var numbers = [5, 6];  
  
// Call the showResults callback function for each array element.  
// The obj is the this value within the   
// callback function.  
numbers.forEach(obj.showResults, obj);  
  
// Embed the callback function in the forEach statement.  
// The obj argument is the this value within the obj object.  
// The output is the same as for the previous statement.  
numbers.forEach(function(value, index) { this.showResults(value, index) }, obj);  
  
// Output:  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [filter 메서드\(Array\)](../../javascript/reference/filter-method-array-javascript.md)   
 [map 메서드\(Array\)](../../javascript/reference/map-method-array-javascript.md)   
 [some 메서드\(Array\)](../../javascript/reference/some-method-array-javascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)   
 [Hilo JavaScript 샘플 응용 프로그램\(Windows 스토어\)](http://hilojs.codeplex.com/SourceControl/latest)