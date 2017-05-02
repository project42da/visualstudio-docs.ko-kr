---
title: "Array.isArray 함수(JavaScript) | Microsoft Docs"
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
  - "Array.isArray 함수[JavaScript]"
  - "isArray 함수[JavaScript]"
ms.assetid: 58f7d2e0-d310-4292-b9bc-37a73c585780
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Array.isArray 함수(JavaScript)
개체가 배열인지 여부를 결정합니다.  
  
## 구문  
  
```  
Array.isArray(object)   
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  테스트할 개체입니다.  
  
## 반환 값  
 `object`가 배열이면 `true`이고, 그렇지 않으면 `false`입니다.  `object` 인수가 개체가 아니면 `false`가 반환됩니다.  
  
## 예제  
 다음 예제에서는 `Array.isArray` 함수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var ar = [];  
var result = Array.isArray(ar);  
// Output: true  
  
var ar = new Array();  
var result = Array.isArray(ar);  
// Output: true  
  
var ar = [1, 2, 3];  
var result = Array.isArray(ar);  
// Output: true  
  
var result = Array.isArray("an array");  
document.write(result);  
// Output: false  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)   
 [typeof 연산자](../../javascript/reference/typeof-operator-decrementjavascript.md)