---
title: "pop 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "pop"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Pop 메서드"
ms.assetid: 4fae7f98-29f1-4041-ba43-601f2e5145ec
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# pop 메서드(Array)(JavaScript)
배열에서 마지막 요소를 제거하여 반환합니다.  
  
## 구문  
  
```  
  
arrayObj.pop( )  
```  
  
## 설명  
 [push](../../javascript/reference/push-method-array-javascript.md) 및 `pop` 메서드를 사용하면 LIFO\(후입 선출\) 원칙을 통해 데이터를 저장하는 스택을 시뮬레이션할 수 있습니다.  
  
 필수 `arrayObj` 참조는 `Array` 개체입니다.  
  
 배열이 비어 있으면 `undefined`가 반환됩니다.  
  
## 예제  
 다음 예제에서는 `pop` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var number;  
var my_array = new Array();  
  
my_array.push (5, 6, 7);  
my_array.push (8, 9);  
  
number = my_array.pop();  
while (number != undefined)  
   {  
   document.write (number + " ");  
   number = my_array.pop();  
   }  
  
// Output: 9 8 7 6 5  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [push 메서드\(Array\)](../../javascript/reference/push-method-array-javascript.md)