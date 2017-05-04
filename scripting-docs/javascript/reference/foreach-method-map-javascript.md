---
title: "forEach 메서드(Map)(JavaScript) | Microsoft Docs"
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
ms.assetid: 9cdf0adc-77c7-4407-8ba7-ada0fb09e507
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# forEach 메서드(Map)(JavaScript)
맵의 각 요소에 대해 지정된 작업을 수행합니다.  
  
## 구문  
  
```javascript  
mapObj.forEach(callbackfn[, thisArg])  
```  
  
#### 매개 변수  
 `mapObj`  
 필수 요소.  `Map` 개체  
  
 `callbackfn`  
 필수 요소.  맵에 있는 각 요소에 대해 `forEach`에서 한 번씩 호출되는 함수입니다.  `callbackfn`에는 세 가지 인수가 적용됩니다.  `forEach`는 맵에 있는 각 요소마다 한 번씩 `callbackfn` 함수를 호출합니다.  
  
 `thisArg`  
 선택 사항입니다.  `this` 키워드가 `callbackfn` 함수에서 참조할 수 있는 개체입니다.  `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.  
  
## 예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 콜백 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, key, mapObj)`  
  
 다음 표와 같이 최대 세 개의 매개 변수를 사용하여 콜백 함수를 선언할 수 있습니다.  
  
|콜백 인수|정의|  
|-----------|--------|  
|`value`|맵에 포함된 값입니다.|  
|`key`|맵에 포함된 키입니다.|  
|`mapObj`|이동할 `Map` 개체입니다.|  
  
## 예제  
 다음 예제에서는 `forEach`를 사용하여 `Map` 멤버를 검색하는 방법을 보여 줍니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (item, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]