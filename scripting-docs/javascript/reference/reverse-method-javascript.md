---
title: "reverse 메서드(JavaScript) | Microsoft Docs"
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
  - "reverse"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "배열[Visual Studio], 요소 되돌리기"
  - "reverse 메서드"
  - "요소 바꾸기"
ms.assetid: 02ab051b-79b8-4646-b502-381671e78c12
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# reverse 메서드(JavaScript)
`Array`의 요소 순서를 반대로 바꿉니다  
  
## 구문  
  
```  
  
arrayObj.reverse()   
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  임의의 `Array` 개체입니다.  
  
## 반환 값  
 역순 배열입니다.  
  
## 설명  
 필수 `arrayObj` 참조는 `Array` 개체입니다.  
  
 `reverse` 메서드는 `Array` 개체의 요소 순서를 반대로 바꿉니다.  실행 도중 새 `Array` 개체를 만들지 않습니다.  
  
 배열이 연속적이지 않으면 `reverse` 메서드는 배열의 간격을 채우는 배열 요소를 만듭니다.  이렇게 만들어진 각 요소에는 `undefined` 값이 있습니다.  
  
## 예제  
 다음 예제에서는 `reverse` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var arr = new Array(0,1,2,3,4);   
var reverseArr = arr.reverse();  
document.write(reverseArr);  
  
// Output:  
// 4,3,2,1,0  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [concat 메서드\(Array\)](../../javascript/reference/concat-method-array-javascript.md)