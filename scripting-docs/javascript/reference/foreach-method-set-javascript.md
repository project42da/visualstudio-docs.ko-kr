---
title: "forEach 메서드(Set)(JavaScript) | Microsoft Docs"
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
ms.assetid: 813bff6e-6098-4260-ab6e-b0d2da6be94d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# forEach 메서드(Set)(JavaScript)
집합의 각 요소에 대해 지정된 작업을 수행합니다.  
  
## 구문  
  
```javascript  
setObj.forEach(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
 `setObj`  
 필수 요소.  `Set` 개체  
  
 `callbackfn`  
 필수 요소.  `callbackfn`에는 세 가지 인수가 적용됩니다.  해당 집합에 있는 각 요소에 대해 `forEach`가 한 번씩 호출하는 함수입니다.  
  
 `thisArg`  
 선택 사항입니다.  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, key, setObj)`  
  
 다음 표와 같이 최대 세 개의 매개 변수를 사용하여 콜백 함수를 선언할 수 있습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`value`|집합에 포함된 값입니다.|  
|`key`|집합에 포함된 값입니다.  집합에는 키가 없으므로 이 값은 `value`와 동일합니다.|  
|`setObj`|이동할 `Set` 개체입니다.|  
  
## 예제  
 다음 예제에서는 `forEach`의 사용 방법을 보여 줍니다.  `callbackfn` 인수는 콜백 함수에 대한 코드를 포함합니다.  
  
```javascript  
var s = new Set();  
  
s.add("scale");  
s.add(10);  
s.add("5");  
  
s.forEach(function(item, sameItem, s) {  
    document.write("Size of the set object is: " + s.size + "<br />");  
    document.write("Deleting item: " + item + "<br />");  
    s.delete(sameItem);  
});  
  
// Output:  
// Size of the set object is: 3  
// Deleting item: scale  
// Size of the set object is: 2  
// Deleting item: 10  
// Size of the set object is: 1  
// Deleting item: 5  
```  
  
## 예제  
 다음 예제에서는 단일 매개 변수를 콜백 함수에 전달하여 집합에서 멤버를 검색할 수도 있음을 보여 줍니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]