---
title: "Array.from 함수(Array)(JavaScript) | Microsoft Docs"
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
ms.assetid: 1bf59a99-f860-4c4d-b4c6-d5f1f946a490
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Array.from 함수(Array)(JavaScript)
배열 형식의 개체나 반복 가능한 개체에서 배열을 반환합니다.  
  
## 구문  
  
```  
Array.from (arrayLike [ , mapfn [ , thisArg ] ] );  
```  
  
#### 매개 변수  
 `arrayLike`  
 필수 요소.  배열 형식의 개체나 반복 가능한 개체입니다.  
  
 `mapfn`  
 선택적 요소.  `arrayLike`의 각 요소에 대해 호출할 매핑 함수입니다.  
  
 `thisArg`  
 선택적 요소.  매핑 함수에 `this` 개체를 지정합니다.  
  
## 설명  
 `arrayLike` 매개 변수는 인덱싱된 요소 및 `length` 속성을 가진 개체이거나 `Set` 개체와 같은 반복 가능한 개체여야 합니다.  
  
 선택적 매핑 함수는 배열의 각 요소에 대해 호출됩니다.  
  
## 예제  
 다음 예제에서는 DOM 요소 노드 컬렉션에서 배열을 반환합니다.  
  
```javascript  
var elemArr = Array.from(document.querySelectorAll('*'));  
var elem = elemArr[0]; // elem contains a reference to the first DOM element  
  
```  
  
## 예제  
 다음 예제에서는 문자 배열을 반환합니다.  
  
```javascript  
var charArr = Array.from("abc");  
// charArr[0] == "a";  
```  
  
## 예제  
 다음 예제에서는 컬렉션에 포함된 개체의 배열을 반환합니다.  
  
```javascript  
var setObj = new Set("a", "b", "c");  
var objArr = Array.from(setObj);  
// objArr[1] == "b";  
  
```  
  
## 예제  
 다음 예제에서는 화살표 구문 및 매핑 함수를 사용하여 요소의 값을 변경하는 방법을 보여 줍니다.  
  
```javascript  
var arr = Array.from([1, 2, 3], x => x * 10);  
// arr[0] == 10;  
// arr[1] == 20;  
// arr[2] == 30;  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]