---
title: "for...in 문(JavaScript) | Microsoft Docs"
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
  - "반복문, for...in 문"
  - "루프 구조, for...in 문"
ms.assetid: 1b51a0ce-89f7-4a69-88ed-017b47dc398f
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# for...in 문(JavaScript)
개체의 각 속성이나 배열의 각 요소에 대해 하나 이상의 문을 실행합니다.  
  
## 구문  
  
```  
for (variable in [object | array]) {  
    statements   
}  
```  
  
## 매개 변수  
 `variable`  
 필수 요소.  `object`의 속성 이름 또는 `array`의 요소 인덱스일 수 있는 변수입니다.  
  
 `object`, `array`  
 선택 사항입니다.  반복할 개체 또는 배열입니다.  
  
 `statements`  
 선택 사항입니다.  `object`의 각 속성 또는 `array`의 각 요소에 실행할 하나 이상의 문입니다.  복합 문도 가능합니다.  
  
## 설명  
 루프의 각 반복 시작 부분에서 `variable`의 값은 `object`의 다음 속성 이름이거나 `array`의 다음 요소 인덱스입니다.  루프 안에 있는 문에서 `variable`을 사용하여 `object`의 속성 또는 `array`의 요소를 참조할 수 있습니다.  
  
 개체의 속성은 종료 형식으로 할당되지 않습니다.  인덱스, 속성의 이름만으로 특정 속성을 지정할 수 없습니다.  
  
 배열에 대한 반복은 요소 순서인 0, 1, 2로 수행됩니다.  
  
## 예제  
 다음 예제는 연결 배열로 사용되는 개체가 있는 `for...in` 문을 사용하는 방법을 보여 줍니다.  
  
```javascript  
// Initialize object.  
a = {"a" : "Athens" , "b" : "Belgrade", "c" : "Cairo"}  
  
// Iterate over the properties.  
var s = ""  
for (var key in a) {  
    s += key + ": " + a[key];  
    s += "<br />";  
    }  
document.write (s);  
  
// Output:  
// a: Athens  
// b: Belgrade  
// c: Cairo  
```  
  
## 예제  
 이 예제에서는 expando 속성이 있는 `Array` 개체를 통해 반복하도록 `for ... in` 문을 사용하는 방법을 설명합니다.  
  
```javascript  
// Initialize the array.  
var arr = new Array("zero","one","two");  
  
// Add a few expando properties to the array.  
arr["orange"] = "fruit";  
arr["carrot"] = "vegetable";  
  
// Iterate over the properties and elements.  
var s = "";  
for (var key in arr) {  
    s += key + ": " + arr[key];  
    s += "<br />";  
}  
  
document.write (s);  
  
// Output:  
//   0: zero  
//   1: one  
//   2: two  
//   orange: fruit  
//   carrot: vegetable  
```  
  
> [!NOTE]
>  컬렉션 멤버를 반복할 `Enumerator` 개체를 사용합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## 참고 항목  
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)