---
title: "Array 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Array"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Array 개체"
  - "constructor 속성"
ms.assetid: 08e5f552-0797-4b48-8164-609582fc18c9
caps.latest.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 27
---
# Array 개체(JavaScript)
임의 데이터 형식의 배열 생성을 지원합니다.  
  
## 구문  
  
```  
  
        arrayObj = new Array()  
arrayObj = new Array([size])  
arrayObj = new Array([element0[, element1[, ...[, elementN]]]])  
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  `Array` 개체가 할당되는 변수 이름입니다.  
  
 `size`  
 선택적 요소.  배열의 크기입니다.  배열이 0부터 시작하기 때문에 생성된 요소의 인덱스는 0부터 `size` \-1까지입니다.  
  
 `element0,...,elementN`  
 선택적 요소.  배열에 배치할 요소입니다.  그러면 *n* \+ 1개 요소를 포함하고 `length`가 *n* \+ 1인 배열이 생성됩니다.  이 구문을 사용하여 요소를 두 개 이상 제공해야 합니다.  
  
## 설명  
 배열이 생성된 후 \[ \] 표기법을 사용하여 배열의 개별 요소에 액세스할 수 있습니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 배열은 0부터 시작합니다.  
  
```javascript  
var my_array = new Array();  
for (i = 0; i < 10; i++) {  
    my_array[i] = i;  
}  
x = my_array[4];  
document.write(x);  
  
// Output: 4  
```  
  
 부호 없는 32비트 정수를 `Array` 생성자에 전달하여 배열의 크기를 지정할 수 있습니다.  값이 음수이거나 정수가 아닌 경우 런타임 오류가 발생합니다.  다음 코드를 실행하는 경우 이 오류가 콘솔에 표시되어야 합니다.  
  
```javascript  
var arr = new Array(10);  
document.write(arr.length);  
  
// Output: 10  
  
// Don't do this  
var arr = new Array(-1);  
arr = new Array(1.50);   
```  
  
 단일 값이 `Array` 생성자에 전달되고 숫자가 아닌 경우 `length` 속성이 1로 설정되며, 유일한 요소의 값은 전달된 단일 인수가 됩니다.  
  
```npl  
var arr = new Array("one");  
document.write(arr.length);  
document.write("<br/>");  
document.write(arr[0]);  
  
// Output:  
1  
one  
  
```  
  
 JavaScript 배열은 스파스 배열이므로 배열에 데이터를 포함하지 않은 요소가 있을 수 있습니다.  JavaScript에서는 실제로 데이터를 포함하는 요소만 배열에 들어 있습니다.  이렇게 하면 배열에서 사용되는 메모리 양이 줄어듭니다.  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 다음 목록의 일부 멤버는 이후 버전에서 도입되었습니다.  자세한 내용은 [버전 정보](../../javascript/reference/javascript-version-information.md) 또는 개별 멤버에 대한 설명서를 참조하세요.  
  
## 속성  
 다음 표에서는 `Array` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[constructor 속성](../../javascript/reference/constructor-property-array.md)|배열을 만드는 함수를 지정합니다.|  
|[Length 속성\(Array\)](../../javascript/reference/length-property-array-javascript.md)|배열에 정의된 가장 큰 요소보다 1이 큰 정수 값을 반환합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-array.md)|배열의 프로토타입에 대한 참조를 반환합니다.|  
  
## 함수  
 다음 표에서는 `Array` 개체의 함수를 설명합니다.  
  
|함수|설명|  
|--------|--------|  
|[Array.from 함수](../../javascript/reference/array-from-function-array-javascript.md)|배열 형식의 개체나 반복 가능한 개체에서 배열을 반환합니다.|  
|[Array.isArray 함수](../../javascript/reference/array-isarray-function-javascript.md)|개체가 배열인지 여부를 나타내는 부울 값을 반환합니다.|  
|[Array.of 함수](../../javascript/reference/array-of-function-array-javascript.md)|전달된 인수에서 배열을 반환합니다.|  
  
<a name="js56jsobjarraymeth"></a>   
## 메서드  
 다음 표에서는 `Array` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[concat 메서드\(Array\)](../../javascript/reference/concat-method-array-javascript.md)|두 배열의 조합으로 이루어진 새 배열을 반환합니다.|  
|[entries 메서드](../../javascript/reference/entries-method-array-javascript.md)|배열의 키\/값 쌍을 포함하는 반복기를 반환합니다.|  
|[every 메서드](../../javascript/reference/every-method-array-javascript.md)|정의된 호출 함수가 배열의 모든 요소에 대해 `true`를 반환하는지 여부를 확인합니다.|  
|[fill 메서드](../../javascript/reference/fill-method-array-javascript.md)|지정된 값으로 배열을 채웁니다.|  
|[filter 메서드](../../javascript/reference/filter-method-array-javascript.md)|배열의 각 요소에 대해 정의된 호출 함수를 호출하고 호출 함수가 `true`를 반환하는 값의 배열을 반환합니다.|  
|[FindIndex 메서드](../../javascript/reference/findindex-method-array-javascript.md)|호출 함수에 지정된 테스트 조건을 충족하는 첫 번째 배열 요소의 인덱스 값을 반환합니다.|  
|[forEach 메서드](../../javascript/reference/foreach-method-array-javascript.md)|배열의 각 요소에 대해 정의된 호출 함수를 호출합니다.|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[IndexOf 메서드\(Array\)](../../javascript/reference/indexof-method-array-javascript.md)|배열에서 맨 처음 발견되는 값의 인덱스를 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 체인에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[Join 메서드](../../javascript/reference/join-method-array-javascript.md)|서로 연결된 배열의 모든 요소로 이루어진 `String` 개체를 반환합니다.|  
|[keys 메서드](../../javascript/reference/keys-method-array-javascript.md)|배열의 인덱스 값을 포함하는 반복기를 반환합니다.|  
|[LastIndexOf 메서드](../../javascript/reference/lastindexof-method-array-javascript.md)|배열에서 마지막으로 발견되는 지정된 값의 인덱스를 반환합니다.|  
|[map 메서드](../../javascript/reference/map-method-array-javascript.md)|배열의 각 요소에 대해 정의된 호출 함수를 호출하고 결과가 포함된 배열을 반환합니다.|  
|[pop 메서드](../../javascript/reference/pop-method-array-javascript.md)|배열에서 마지막 요소를 제거하고 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지 여부 및 열거 가능한지 여부를 나타내는 부울 값을 반환합니다.|  
|[push 메서드](../../javascript/reference/push-method-array-javascript.md)|배열에 새 요소를 추가하고 배열의 새 길이를 반환합니다.|  
|[reduce 메서드](../../javascript/reference/reduce-method-array-javascript.md)|배열의 모든 요소에 대해 정의된 호출 함수를 호출하여 단일 결과를 누적합니다.  호출 함수의 반환 값은 누적된 결과이며, 호출 함수에 대한 다음 호출에서 인수로 제공됩니다.|  
|[reduceRight 메서드](../../javascript/reference/reduceright-method-array-javascript.md)|내림차순으로 배열의 모든 요소에 대해 정의된 호출 함수를 호출하여 단일 결과를 누적합니다.  호출 함수의 반환 값은 누적된 결과이며, 호출 함수에 대한 다음 호출에서 인수로 제공됩니다.|  
|[reverse 메서드](../../javascript/reference/reverse-method-javascript.md)|요소가 반대 순서로 지정된 `Array` 개체를 반환합니다.|  
|[shift 메서드](../../javascript/reference/shift-method-array-javascript.md)|배열에서 첫 번째 요소를 제거하고 반환합니다.|  
|[slice 메서드\(Array\)](../../javascript/reference/slice-method-array-javascript.md)|배열의 한 섹션을 반환합니다.|  
|[some 메서드](../../javascript/reference/some-method-array-javascript.md)|정의된 호출 함수가 배열의 임의 요소에 대해 `true`를 반환하는지 여부를 확인합니다.|  
|[sort 메서드](../../javascript/reference/sort-method-array-javascript.md)|요소가 정렬된 `Array` 개체를 반환합니다.|  
|[splice 메서드](../../javascript/reference/splice-method-array-javascript.md)|배열에서 요소를 제거한 다음, 필요한 경우 새 요소를 그 자리에 삽입하고 삭제된 요소를 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-method-object-javascript.md)|현재 로캘을 사용하여 문자열을 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-array.md)|배열의 문자열 표현을 반환합니다.|  
|[unshift 메서드](../../javascript/reference/unshift-method-array-javascript.md)|배열의 시작 부분에 새 요소를 삽입합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-array.md)|배열에 대한 참조를 가져옵니다.|  
|[values 메서드](../../javascript/reference/values-method-array-javascript.md)|배열의 값을 포함하는 반복기를 반환합니다.|  
  
## 참고 항목  
 [샘플 앱 스크롤, 이동 및 확대\/축소](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)