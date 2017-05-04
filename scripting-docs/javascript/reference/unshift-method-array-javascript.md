---
title: "unshift 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "unshift"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "unshift 메서드"
ms.assetid: 8c6a39ed-bab3-4ca4-9350-571a9427ec94
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# unshift 메서드(Array)(JavaScript)
배열 시작에 새 요소를 삽입합니다.  
  
## 구문  
  
```  
  
arrayObj.unshift([item1[, item2 [, . . . [, itemN]]]])  
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  `Array` 개체입니다.  
  
 `item1, item2,. . ., itemN`  
 선택 사항입니다.  `Array` 의 시작 부분에 삽입할 요소입니다.  
  
## 설명  
 `unshift` 메서드는 배열의 시작 부분에 요소를 삽입하여 인수 목록에 표시되는 순서대로 표시합니다.  
  
## 예제  
 다음 예제에서는 `unshift` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var ar = new Array();  
ar.unshift(10, 11);  
ar.unshift(12, 13, 14);  
document.write(ar.toString());  
  
// Output: 12,13,14,10,11  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [shift 메서드\(Array\)](../../javascript/reference/shift-method-array-javascript.md)