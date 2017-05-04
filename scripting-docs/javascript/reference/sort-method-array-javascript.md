---
title: "sort 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "sort"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Sort 메서드"
ms.assetid: 9bd8b54a-c838-4806-85c8-62eebe6bc48c
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# sort 메서드(Array)(JavaScript)
`Array`를 정렬합니다.  
  
## 구문  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  임의의 `Array` 개체입니다.  
  
 `sortFunction`  
 선택 사항입니다.  요소 순서를 결정하는 데 사용되는 함수의 이름입니다.  인수를 생략하면 요소가 오름차순, ASCII 문자 순서로 정렬됩니다.  
  
## 반환 값  
 정렬된 배열입니다.  
  
## 설명  
 `sort` 메서드는 `Array` 개체를 제자리에 정렬하지만 실행 중에 새로운 `Array` 개체를 만들지는 않습니다.  
  
 `sortFunction` 인수에 함수를 지정하면 다음 값 중 하나가 반환됩니다.  
  
-   처음 전달된 인수가 두 번째 인수보다 작을 경우 음수 값  
  
-   두 인수가 같을 경우 0  
  
-   처음 전달된 인수가 두 번째 인수보다 클 경우 양수 값  
  
## 예제  
 다음 예제에서는 `sort` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var a = new Array(4, 11, 2, 10, 3, 1);  
  
var b = a.sort();  
document.write(b);  
document.write("<br/>");  
  
// This is ASCII character order.  
// Output: 1,10,11,2,3,4)  
  
// Sort the array elements with a function that compares array elements.  
b = a.sort(CompareForSort);  
document.write(b);  
document.write("<br/>");  
// Output: 1,2,3,4,10,11.  
  
// Sorts array elements in ascending order numerically.  
function CompareForSort(first, second)  
{  
    if (first == second)  
        return 0;  
    if (first < second)  
        return -1;  
    else  
        return 1;   
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]