---
title: "indexOf 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "배열[JavaScript], indexOf 메서드"
  - "indexOf 메서드[JavaScript]"
ms.assetid: 5bee31ae-aaf1-4466-8cfd-ed287e3cdf17
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# indexOf 메서드(Array)(JavaScript)
배열에서 맨 처음 나오는 값의 인덱스를 반환합니다.  
  
## 구문  
  
```  
  
array1.indexOf(searchElement[, fromIndex])  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`array1`|필수 요소.  Array 개체입니다.|  
|`searchElement`|필수 요소.  `array1`에서 찾을 값입니다.|  
|`fromIndex`|선택 사항입니다.  검색을 시작할 배열 인덱스입니다.  `fromIndex`가 생략되면 검색이 인덱스 0에서 시작됩니다.|  
  
## 반환 값  
 배열에서 `searchElement`의 처음에 나타나는 인덱스 또는 `searchElement`가 없는 경우 \-1입니다.  
  
## 설명  
 `indexOf` 메서드는 지정한 값에 대한 배열을 검색합니다.  메서드는 첫 번째 나타나는 인덱스를 반환하거나 지정된 값이 없는 경우 \-1을 반환합니다.  
  
 검색은 오름차순 인덱스 순서로 수행됩니다.  
  
 배열 요소는 `===` 연산자와 비슷한 완전 같음으로 발생한 `searchElement` 값과 비교됩니다.  자세한 내용은 [비교 연산자](../../javascript/reference/comparison-operators-javascript.md)를 참조하세요.  
  
 선택적 `fromIndex` 인수는 검색을 시작할 배열 인덱스를 지정합니다.  `fromIndex`가 배열 길이보다 크거나 같으면 \-1이 반환됩니다.  `fromIndex`가 음수이면 검색이 배열 길이 및 `fromIndex`에서 시작됩니다.  
  
## 예제  
 다음 예제에서는 `indexOf` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
// Create an array. (The elements start at index 0.)  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location of "cd".  
document.write(ar.indexOf("cd") + "<br/>");  
  
// Output: 1  
  
// Find "cd" starting at index 2.  
document.write(ar.indexOf("cd", 2) + "<br/>");  
  
// Output: 4  
  
// Find "gh" (which is not found).  
document.write (ar.indexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -2.  
// The search starts at index 3, which is the array length plus -2.  
document.write (ar.indexOf("ab", -2) + "<br/>");  
// Output: 3  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)