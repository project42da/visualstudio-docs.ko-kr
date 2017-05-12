---
title: "Array.of 함수(Array)(JavaScript) | Microsoft Docs"
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
ms.assetid: 2884dda3-65d1-4990-9afe-87865c2d4f7f
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Array.of 함수(Array)(JavaScript)
전달된 인수에서 배열을 반환합니다.  
  
## 구문  
  
```  
Array.of(element0[, element1][, ...][,elementN]);  
```  
  
#### 매개 변수  
 `element0,...,elementN`  
 선택적 요소.  배열에 배치할 요소입니다.  n \+ 1개의 요소를 포함하고 길이가 n \+ 1인 배열이 생성됩니다.  
  
## 설명  
 이 함수는 `new Array(args)` 호출과 비슷하지만 `Array.of`는 하나의 인수가 전달된 경우 특수 동작을 포함하지 않습니다.  
  
## 예제  
 다음 예제에서는 전달된 숫자에서 배열을 만듭니다.  
  
```javascript  
var arr = Array.of(1, 2, 3);  
// arr[0] == 1  
  
```  
  
## 예제  
 다음 예제에서는 `Array.of` 및 `new Array` 사용의 차이점을 보여 줍니다.  
  
```javascript  
var arr1 = Array.of(3);  
// arr1[0] == 3  
  
// With new Array, a single argument specifies  
// the length of the new array.  
var arr2 = new Array(3);  
// arr2[0] is undefined  
// arr2.length == 3  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]